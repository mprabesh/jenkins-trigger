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
                script {
                    // Different build steps based on the branch name
                    if (env.BRANCH_NAME == 'main') {
                        sh 'sleep 7'
                        echo 'Building for production...'
                        // Add production build steps here
                    } else {
                        sh 'sleep 3'
                        echo "Building for branch: ${env.BRANCH_NAME}"
                        // Add branch-specific build steps here
                    }
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    if (env.BRANCH_NAME == 'dev' || env.BRANCH_NAME.startsWith('feature/')) {
                        sh 'sleep 3'
                        echo 'Running tests...'
                        // Add test steps here
                    }
                }
            }
        }
        
        stage('Deploy') {
            steps {
                script {
                    if (env.BRANCH_NAME == 'dev') {
                        sh 'sleep 3'
                        echo 'Deploying to staging...'
                        // Add staging deployment steps here
                    } else if (env.BRANCH_NAME == 'main') {
                        sh 'sleep 7'
                        echo 'Deploying to production...'
                        // Add production deployment steps here
                    }
                }
            }
        }
    }
}
