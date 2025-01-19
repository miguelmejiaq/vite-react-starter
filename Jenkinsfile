pipeline {
    agent {
        docker { image 'node:22.13.0-alpine3.21' }
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
    }
}