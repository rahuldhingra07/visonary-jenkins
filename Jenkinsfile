pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from the repository
                checkout scm
            }
        }

        stage('Build') {
            steps {
                dir('path/to/your/project') { // Change to the correct path where your gradlew file is located
                    sh './gradlew build'
                }
            }
        }

        stage('Test') {
            steps {
                dir('path/to/your/project') { // Change to the correct path where your gradlew file is located
                    // Run the tests
                    sh './gradlew test'
                }
            }
        }
    }

    post {
        always {
            // Archive test results and artifacts
            junit 'build/test-results/test/TEST-*.xml' // Adjust path if needed
            archiveArtifacts artifacts: 'build/libs/**/*.jar', fingerprint: true
        }
    }
}
