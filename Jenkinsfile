pipeline {
    agent {
        docker { 
            image 'node:20.17.0-alpine3.20'
            args '-v /var/run/docker.sock:/var/run/docker.sock' // Bind Docker socket for Docker within Docker, if needed
        }
    }
    stages {
        stage('Test') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'node --version'  // Unix/Linux systems
                    } else {
                        bat 'node --version' // Windows systems
                    }
                }
            }
        }
    }
}
