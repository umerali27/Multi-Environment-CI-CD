pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/your-org/multi-env-ci-cd.git'
            }
        }

        stage('Build Docker Images') {
            steps {
                sh 'docker build -t frontend:${BUILD_NUMBER} frontend/'
                sh 'docker build -t backend:${BUILD_NUMBER} backend/'
            }
        }

        stage('Push Docker Images') {
            steps {
                sh 'docker tag frontend:${BUILD_NUMBER} frontend:latest'
                sh 'docker tag backend:${BUILD_NUMBER} backend:latest'
            }
        }

        stage('Deploy to DEV') {
            steps {
                sh '''
                helm upgrade --install myapp-dev helm-chart \
                -f helm-chart/values-dev.yaml \
                --namespace dev --create-namespace
                '''
            }
        }

        stage('Deploy to STAGING') {
            steps {
                sh '''
                helm upgrade --install myapp-staging helm-chart \
                -f helm-chart/values-staging.yaml \
                --namespace staging --create-namespace
                '''
            }
        }

        stage('Approval for PROD') {
            steps {
                input message: 'Approve deployment to PROD'
            }
        }

        stage('Deploy to PROD') {
            steps {
                sh '''
                helm upgrade --install myapp-prod helm-chart \
                -f helm-chart/values-prod.yaml \
                --namespace prod --create-namespace
                '''
            }
        }
    }
}
