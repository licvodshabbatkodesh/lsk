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
                withCredentials([aws(accessKeyVariable:'AWS_ACCESS_KEY_ID',credentialsId:'darinpope-aws-creds',secretKeyVariable:'AWS_SECRET_ACCESS_KEY')]){
                sh '''
                aws --version
                aws ec2 describe-instances
                '''
                }
       
                
            }
        }
    }
}