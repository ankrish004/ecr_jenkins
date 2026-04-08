pipeline {
    agent any

    stages {

        stage('Node Setup') {
            agent {
                docker {
                    image 'node:18-alpine'
                }
            }
            steps {
                sh '''
                 node -v
                 '''
            }
        }

        stage('AWS') {
            agent {
                docker {
                    image 'amazon/aws-cli:2.34.26'
                }
            }
            steps {
                sh '''
                aws --version
                aws s3 ls
                '''
            }
        }

    }
}