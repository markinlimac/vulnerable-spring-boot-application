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
                    dockerapp = docker.build("markinlimac/vulnerable-spring-boot-application:${env.BUILD_ID}", "-f ./Dockerfile ./")
                }
            }
        }

        // stage ('Deploy') {
        //     steps {
        //         echo 'Implantação do contêiner em um ambiente Kubernetes, utilizando manifestos configurados para o ambiente de staging/testes'
        //     }
        // }
    }
}