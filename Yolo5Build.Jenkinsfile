pipeline {
    agent any
    environment {
        AWS_REGION= 'us-east-2'
        ECR_REGISTRY_URL='854171615125.dkr.ecr.us-east-2.amazonaws.com/nishant-project2'
    }
    stages {
        stage('Build') {
            steps {
                sh 'echo building...'
            }
        }
        stage('Build Yolo5 app') {
            steps {
               sh '''
                    aws ecr get-login-password --region us-east-2 | docker login --username AWS --password-stdin 854171615125.dkr.ecr.us-east-2.amazonaws.com
                    cd Yolo5
                    docker build -t nishant-project2 .
                    docker tag nishant-project2:latest 854171615125.dkr.ecr.us-east-2.amazonaws.com/nishant-project2:latest
                    docker push 854171615125.dkr.ecr.us-east-2.amazonaws.com/nishant-project2:latest

               '''
           }
        }
    }
}