pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat 'echo "Starting Build..."'
                bat 'dir'  // Executes the 'dir' command to list files on Windows
            }
        }

        stage('Test') {
            steps {
                bat 'echo "Running Tests..."'
                bat 'set'  // Example of a command that displays environment variables
            }
        }

        stage('Deploy') {
            steps {
                bat 'echo "Deploying..."'
                bat 'exit /b 0'  // Simulates successful deployment
            }
        }
    }

    post {
        always {
            echo 'This will always run after the stages complete.'
        }
        success {
            echo 'The pipeline succeeded!'
        }
        failure {
            echo 'The pipeline failed.'
        }
    }
}
