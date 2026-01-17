pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/yourusername/multi-tier-app.git'
            }
        }
        stage('Build Docker Images') {
            steps {
                sh 'docker build -t frontend:latest ./frontend'
                sh 'docker build -t backend:latest ./backend'
            }
        }
        stage('Push to Registry') {
            steps {
                sh 'docker tag frontend:latest your-dockerhub/frontend:latest'
                sh 'docker push your-dockerhub/frontend:latest'
                sh 'docker tag backend:latest your-dockerhub/backend:latest'
                sh 'docker push your-dockerhub/backend:latest'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                sh 'helm upgrade --install multi-tier ./k8s/helm-chart'
            }
        }
    }
}

