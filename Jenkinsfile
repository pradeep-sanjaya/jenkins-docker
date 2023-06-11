
pipeline {

    agent any

    environment {
        DOCKERHUB_CREDENTIALS = credentials('dockerhub')
    }

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t ngpsanjaya/alpine:3.18.0 .'
            }
        }

        stage('Login') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }

        stage('Push') {
            steps {
                sh 'docker push ngpsanjaya/alpine:3.18.0'
            }
        }
    }
    post {
        always {
            sh 'docker logout'
        }
    }
}
