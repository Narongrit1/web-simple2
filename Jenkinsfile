// Jenkinsfile
pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/Narongrit1/web-simple2.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-web-cicd .'
            }
        }
        stage('Run Container') {
            steps {
                bat 'docker rm -f my-web || true'
                bat 'docker run -d --name my-web -p 5000:80 my-web-cicd'
            }
        }
    }
}
