pipeline {
    agent any

    stages {

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