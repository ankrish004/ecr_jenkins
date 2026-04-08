pipeline{
    agent any
    stages{
        agent {
    docker {
        image 'node:18-alpine'
            }
        }
        stage ('aws') {
            agent {
                docker {
                    image 'amazon/aws-cli:2.34.26'
                }
            }
            steps{
                sh '''
                aws --version
                aws s3 ls
                aws --version
                '''
            }
        }          
        
    }
}
