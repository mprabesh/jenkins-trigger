pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building started.'
                sh 'sleep 5'
            }
        }
         stage('Test') {
            steps {
                echo 'Testing Started'
                sh 'sleep 3'
            }
        }
         stage('Deploy') {
            steps {
                echo 'Deployment in progress.'
                sh 'sleep 7'
            }
        }
    }
}
