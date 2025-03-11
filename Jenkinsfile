pipeline {
    agent any
    stages {
        stage('Install prerequisites') {
            steps {
                    sh 'npm install'
            }
        }
        stage('Build') {
            steps {
                    sh 'npm build'
            }
        }
    }
}