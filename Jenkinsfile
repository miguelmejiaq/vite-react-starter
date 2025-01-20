pipeline {
    agent none
    tools {
        jfrog 'jfrog-cli'
    }
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