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
                    sh 'mvn sonar:sonar'
                }
            }
        }
        // stage ('Contêinerização') {
        //     steps {
        //         echo 'Criação de uma imagem Docker do aplicativo'
        //     }
        // }
        // stage ('Deploy') {
        //     steps {
        //         echo 'Implantação do contêiner em um ambiente Kubernetes, utilizando manifestos configurados para o ambiente de staging/testes'
        //     }
        // }
    }
}