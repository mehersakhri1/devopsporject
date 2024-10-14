pipeline {
    agent any
    tools {
        maven 'Maven 3.8' // Le nom de votre configuration Maven dans Jenkins
    }
    stages {
        stage('Checkout') {
            steps {
                git credentialsId: 'github-token', url: 'https://github.com/username/repo.git'
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
        stage('Deploy') {
            steps {
                sh 'mvn deploy'
            }
        }
    }
    post {
        success {
            echo 'Build and tests succeeded!'
        }
        failure {
            echo 'Build failed.'
        }
    }
}
