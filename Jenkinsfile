def REMOTE_DIR = ' /var/www/html'

pipeline {
    agent any
    stages {
        stage("Build"){
            steps {
               nodejs('nodejs14'){
                   sh 'npm install'
                   sh 'npm run build'
               }
            }
        }
        stage("Test"){
            steps {
                echo "Testing"
            }
        }
        stage("Deploy"){
            steps {
                script {
                    sshPublisher(
                        publisher; [
                        sshPublisherDesc(
                            configName: 'developmentdesi',
                            verbose: false,
                            transfer: [
                                sshTransfer(
                                    sourceFiles: "dist/*",
                                    execTieout: 120000,
                                )
                            ]
                        )
                    ]
                )
            }
        }
    }
}