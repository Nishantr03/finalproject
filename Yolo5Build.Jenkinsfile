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
                    cd yolo5
                    docker build -t nishant-project2 .
                    docker tag nishant-project2:latest 854171615125.dkr.ecr.us-east-2.amazonaws.com/nishant-project2:${BUILD_NUMBER}
                    docker push 854171615125.dkr.ecr.us-east-2.amazonaws.com/nishant-project2:${BUILD_NUMBER}
               '''
           }
        }
//          stage('Trigger Deploy') {
//              steps {
//                  build job: 'Yolo5Deploy', wait: false, parameters: [
//                      string(name: 'YOLO5_IMAGE_URL', value: "854171615125.dkr.ecr.us-east-2.amazonaws.com/nishant-project2:0.0.1")
//                  ]
//              }
          }
     }
 }
