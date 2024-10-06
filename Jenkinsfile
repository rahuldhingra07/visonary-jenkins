pipeline {
    agent any
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh './gradlew build'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                sh './gradlew test'
            }
        }
        stage('Deploy - Staging') {
            steps {
                echo 'Deploying to Staging...'
                sh './deploy staging'
                sh './run-smoke-tests'
            }
        }
        stage('Sanity check') {
            steps {
                input "Does the staging environment look ok?"
            }
        }
        stage('Deploy - Production') {
            steps {
                echo 'Deploying to Production...'
                sh './deploy production'
            }
        }
    }
}
