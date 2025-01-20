pipeline {
    agent {
        docker {
            image 'node:lts'
        }
    }
    tools {
        jfrog 'jfrog-cli'
    }
    stages {
        stage('Compile application') {
        agent any
            steps {
                sh 'npm install'
            }
        }

    }
}