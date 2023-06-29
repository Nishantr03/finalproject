pipeline {
    agent any
    parameters { string(name: 'YOLO5_IMAGE_URL', defaultValue: '854171615125.dkr.ecr.us-east-2.amazonaws.com/nishant-project2:15', description: 'yolo5-Deploy') }

    stages {
        stage('Deploy') {
            steps {
                 sh '''
                aws eks --region us-east-2 update-kubeconfig --name k8s-batch1
                kubectl config set-context --current --namespace=nishant-ns
                kubectl apply -f Yolo5.yaml
                '''
            }
        }
    }
}