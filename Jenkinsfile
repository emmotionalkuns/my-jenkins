pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment steps go here...'
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded! Deployed to production.'
        }
        failure {
            echo 'Pipeline failed. Please check the logs for details.'
        }
    }
}
