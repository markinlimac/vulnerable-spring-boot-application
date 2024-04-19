pipeline {
    agent any

    stages {
        stage ('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }

        stage ('Testes Unitários') {
            steps {
                sh 'mvn test'
            }
        }

        stage ('Análise de Qualidade de Código') {
            steps {
                withSonarQubeEnv('sonarqube') {
                    sh 'mvn sonar:sonar -Dsonar.organization=markinlimac'
                }
            }
        }

        stage ('Contêinerização') {
            steps {
                script {
                    dockerapp = docker.build("280398/vulnerable-spring-boot-application:${env.BUILD_ID}", "-f ./Dockerfile ./")
                    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
                        dockerapp.push('latest')
                        dockerapp.push("${env.BUILD_ID}")
                    }
                }
            }
        }

        stage ('Deploy') {
            environment {
                tag_version = "${env.BUILD_ID}"
            }
            steps {
                withKubeConfig([credentialsId: 'kubeconfig']) {
                    sh 'sed -i "s/{{tag}}/$tag_version/g" ./k8s/deployment.yaml'
                    sh 'kubectl apply -f ./k8s/deployment.yaml'
                }
            }
        }
    }
}