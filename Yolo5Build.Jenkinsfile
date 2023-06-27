pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'echo building...'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
    }
}