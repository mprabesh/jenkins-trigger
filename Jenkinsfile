pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Build') {
            when {
                expression { env.BRANCH_NAME != 'main' }
            }
            steps {
                echo "Building ${env.BRANCH_NAME} branch"
                sh "sleep 2"
            }
        }
        
        stage('Test') {
            when {
                anyOf {
                    branch 'develop'
                    branch pattern: "feature/.*", comparator: "REGEXP"
                }
            }
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
                echo "Deploying main branch exe"
                sh "sleep 3"
            }
        }
    }
}
