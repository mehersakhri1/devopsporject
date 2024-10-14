pipeline {
    agent any 
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/mehersakhri1/devopsporject.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
    }
    post {
        always {
            junit '**/target/surefire-reports/*.xml'
        }
    }
}
