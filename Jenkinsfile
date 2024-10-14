pipeline {
    agent any

    environment {
        GIT_CREDENTIALS_ID = 'github-tok'
        PATH = "/opt/maven/bin:${env.PATH}" // Ajoutez le chemin Maven ici
    }

    stages {
        stage('Clone Repository') {
            steps {
                script {
                    git branch: 'main', url: 'https://github.com/mehersakhri1/devopsporject.git', credentialsId: GIT_CREDENTIALS_ID
                }
            }
        }
        stage('Build with Maven') {
            steps {
                script {
                    // Exécutez Maven pour compiler le projet et exécuter les tests
                    sh 'mvn clean install'
                }
            }
        }
    }

    post {
        success {
            echo 'Build successful! Tests passed!'
        }
        failure {
            echo 'Build failed. Please check the logs for details.'
        }
    }
}
