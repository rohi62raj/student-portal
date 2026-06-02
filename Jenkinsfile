pipeline {

    agent any

    stages {

        stage('Clone Repository') {
            steps {
                echo 'Cloning Repository'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t student-portal:v1 .'
            }
        }

        stage('Verify Kubernetes') {
            steps {
                bat 'kubectl get pods'
            }
        }

        stage('Deploy Application') {
            steps {
                bat 'kubectl apply -f deployment.yaml'
            }
        }

    }

}