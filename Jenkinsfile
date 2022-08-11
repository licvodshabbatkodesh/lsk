pipeline{
    agent{
        node{
            label 'linux'
        }
    }
    environment{
        AWS_DEFAULT_REGION='us-east-1'
    }
    stages{
        stage('Hello'){
            steps{
            withCredentials([[$class: "AmazonWebServicesCredentialsBinding", credentialsId: configuration.release.staging.credentialsId]]) {
                 sh '''
                aws --version
                aws ec2 describe-instances
                '''
                }
            }
        }
    }
}