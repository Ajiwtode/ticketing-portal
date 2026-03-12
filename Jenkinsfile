pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/Ajiwtode/ticketing-portal.git'
            }
        }

        stage('Build Backend Image') {
            steps {
                sh 'docker build -t ticketing-backend ./backend'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f k8s/backend-deployment.yaml'
                sh 'kubectl apply -f k8s/backend-service.yaml'
            }
        }

    }
}
