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
            }
        }
        stage('Publish Artifact') {
            steps {
                script {
                    // Define the artifact and destination
                    def artifactPath = 'dist/*'  // Adjust path to your artifact
                    def remoteDir = '/var/www/html/'  // Remote directory on VM

                    // Transfer the artifact to the VM using SCP
                    sshPublisher(publishers: [sshPublisherDesc(
                        configName: 'apache-server',  // Refer to the SSH configuration name you set earlier
                        transfers: [sshTransfer(
                            sourceFiles: artifactPath,
                            remoteDirectory: remoteDir,
                            makeEmptyDirs: true,
                            cleanRemote: true
                        )]
                    )])
                }
            }
        }
    }
}