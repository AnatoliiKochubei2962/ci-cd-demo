pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo "Checking out code..."
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "Build stage running..."
                sh 'echo "Hello from Jenkins running in Kubernetes!"'
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                sh '''
                    echo "Test 1: OK"
                    echo "Test 2: OK"
                '''
            }
        }

        stage('Deploy (dummy)') {
            steps {
                echo "Deploy stage (no real deployment, just simulation)"
                sh 'echo "Deployment simulated successfully"'
            }
        }
    }

    post {
        success {
            echo "Pipeline completed successfully 🎉"
        }
        failure {
            echo "Pipeline failed ❌"
        }
    }
}