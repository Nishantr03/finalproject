pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'echo building...'
                sh 'Hello World...'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
    }
}