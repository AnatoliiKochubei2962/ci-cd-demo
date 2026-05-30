pipeline {
    agent any

    environment {
        IMAGE = "Anatoliy.Kochubey2962/ci-cd-demo"
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Test') {
            steps {
                sh 'pip install -r requirements.txt'
                sh 'pytest -v'
            }
        }

        stage('Build Docker') {
            steps {
                sh "docker build -t $IMAGE:latest ."
            }
        }

        stage('Deploy') {
            steps {
                sh 'kubectl apply -f k8s/'
            }
        }
    }
}