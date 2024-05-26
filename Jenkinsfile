pipeline {
    agent any
    stages {
        stage('Deploy') {
            steps {
                script {
                    def remoteDirectory = "/var/www/html"
                    
                    sshPublisher(
                        publishers: [
                            sshPublisherDesc(
                                configName: 'ApacheServer',
                                transfers: [
                                    sshTransfer(
                                        sourceFiles: '**/*.html',
                                        remoteDirectory: remoteDirectory,
                                        removePrefix: '',
                                        execCommand: ''
                                    )
                                ],
                                usePromotionTimestamp: false,
                                useWorkspaceInPromotion: false,
                                verbose: true
                            )
                        ]
                    )
                }
            }
        }
    }
}
