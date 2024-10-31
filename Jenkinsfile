pipeline {
    agent any

    parameters {
        choice(name: 'ENVIRONMENT', choices: ['development', 'staging', 'production'], description: 'Select the target environment')
        string(name: 'VERSION', defaultValue: '1.0.0', description: 'Enter the version to deploy')
    }

    stages {
        stage('Build') {
            steps {
                echo "Building version ${params.VERSION} for environment ${params.ENVIRONMENT}"
                sh "sleep 3"
            }
        }

        stage('Test') {
            steps {
                echo "Running tests for version ${params.VERSION} in ${params.ENVIRONMENT} environment"
                // Your test commands go here
                sh "sleep 3"
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying version ${params.VERSION} to ${params.ENVIRONMENT} environment"
                // Your deployment commands go here
                sh "sleep 3"
            }
        }
    }

    post {
        success {
            echo "Pipeline completed successfully."
        }
        failure {
            echo "Pipeline failed."
        }
    }
}
