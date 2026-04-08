pipeline {
    agent any

    stages {

        stage('AWS') {
            agent {
                docker {
                    image 'amazon/aws-cli:2.34.26'
                    args "--entrypoint=''"
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