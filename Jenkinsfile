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
                sh './gradlew build'
            }
        }

        stage('Test') {
            steps {
                sh './gradlew test'
            }
        }

        stage('Deploy') {
            steps {
                
                echo 'Deploying...'
            }
        }
    }

    post {
        always {
            junit 'build/test-results/test/TEST-*.xml'
            archiveArtifacts artifacts: 'build/libs/**/*.jar', fingerprint: true
        }
    }
}
