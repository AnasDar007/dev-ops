pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/AnasDar007/dev-ops.git', branch: 'main'
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying..'
                sshPublisher(
                    publishers: [
                        sshPublisherDesc(
                            configName: 'AWS Assignment',
                            transfers: [sshTransfer(sourceFiles: '*/', remoteDirectory: '/myapp')],
                
                        )
                    ]
                )
            }
        }
    }
}
