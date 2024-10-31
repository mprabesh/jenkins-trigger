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
                echo "Building ${env.BRANCH_NAME} branch"
                sh "sleep 1"
            }
        }
        
        stage('Test') {
            steps {
                echo "Testing ${env.BRANCH_NAME} branch"
                // Add test steps here
                sh "sleep 2"
            }
        }
        
        stage('Deploy') {
            when {
                branch 'main'
            }
            steps {
                echo "Deploying main branch"
                sh "sleep 3"
            }
        }
    }
}
