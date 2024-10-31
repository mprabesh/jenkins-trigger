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
        main
                echo "Building ${env.BRANCH_NAME} branch"
                sh "sleep 2"
            }
        }
        
        stage('Test') {
            steps {
         main
                echo "Testing ${env.BRANCH_NAME} branch"
                // Add test steps here
                sh "sleep 2"
            }
        }
        
        stage('Deploy') {
          main
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
