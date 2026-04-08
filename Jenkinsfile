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
                withCredentials([usernamePassword(credentialsId: 'aws-id', passwordVariable: 'AWS_SECRET_ACCESS_KEY', usernameVariable: 'AWS_ACCESS_KEY_ID')]) {
                sh '''
                aws --version
                echo "hello world" >> index.html
                aws s3 cp index.html s3://open-project-bucket-5352/index.html
                aws s3 ls
                '''   
                }

            }
        }

    }
}