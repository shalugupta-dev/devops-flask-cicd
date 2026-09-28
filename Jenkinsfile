pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/shalugupta-dev/devops-flask-cicd.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t devops-flask-app .'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker rm -f devops-flask-container || exit 0'
                bat 'docker run -d -p 5000:5000 --name devops-flask-container devops-flask-app'
            }
        }
    }
}