pipeline {
    agent any

    environment {
        GIT_CREDENTIALS_ID = 'github-token'  
    }

    stages {
        stage('Clone Repository') {
            steps {
                script {
                    // Cloner le dépôt Git
                    git branch: 'main', url: 'https://github.com/mehersakhri1/devopsporject.git', credentialsId: GIT_CREDENTIALS_ID
                }
            }
        }
        stage('Build with Maven') {
            steps {
                script {
                    // Exécuter Maven pour construire le projet
                    sh 'mvn clean install'
                }
            }
        }
    }

    post {
        success {
            echo 'Build successful!'
        }
        failure {
            echo 'Build failed.'
        }
    }
}
