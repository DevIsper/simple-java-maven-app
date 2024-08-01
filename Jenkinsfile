pipeline {
    agent any

    tools {
        maven 'Maven 3.8.1' // Altere para a versão do Maven que você 
configurou
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/seu-usuario/seu-repositorio.git' 
// Altere para a URL do seu repositório
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: '**/target/*.jar', 
allowEmptyArchive: true
            junit '**/target/surefire-reports/*.xml'
        }
    }
}

