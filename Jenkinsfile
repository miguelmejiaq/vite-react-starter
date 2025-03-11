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
                sh 'npm run build'
                // List the contents of the dist directory
                sh 'ls -la dist'
            }
        }
        stage('Publish Artifact') {
            steps {
               sshPublisher(publishers: [sshPublisherDesc(
                        configName: 'apache-server',  // Refer to the SSH configuration name you set earlier
                        transfers: [sshTransfer(
                            sourceFiles: 'dist/**',
                            remoteDirectory: '/var/www/html',
                            removePrefix: "dist",
                            verbose: true,
                            execCommand: 'sudo systemctl restart apache2'
                        )],
                        usePromotionTimestamp: false,
                        useWorkspaceInPromotion: false,
                        verbose: true
                )])
            }
        }
    }
}