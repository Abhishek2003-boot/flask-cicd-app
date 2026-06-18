pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git branch: 'main',
                url: 'https://github.com/Abhishek2003-boot/flask-cicd-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t flask-cicd-app .'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker stop flask-app || exit 0'
                bat 'docker rm flask-app || exit 0'
                bat 'docker run -d -p 5000:5000 --name flask-app flask-cicd-app'
            }
        }
    }
}