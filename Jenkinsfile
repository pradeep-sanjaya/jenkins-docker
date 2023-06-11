
pipeline {
    environment {
        DOCKERHUB_CREDENTIALS = credentials('dockerhub')
    }

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t ngpsanjaya/alpine:3.18.0'
            }
        }
    }
}
