pipeline {
    agent none
    stages {
        stage('Compile application') {
            agent {
                label 'node-build'
            }
            steps {
                    sh 'npm install'
            }
        }
    }
}