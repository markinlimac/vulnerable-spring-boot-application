pipeline {
    agent any

    stages {
        stage ('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        // stage ('Testes Unitários') {
        //     steps {
        //         echo 'Execução dos testes unitários do repositório na pipeline'
        //     }
        // }
        // stage ('Análise de Qualidade de Código') {
        //     steps {
        //         echo 'Integração com ferramentas como SonarQube para análise estática de código (pode ser qualquer Lint/SAST)'
        //     }
        // }
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