pipeline {
    agent any

    environment {
        IMAGE_NAME = "devops-app"
    }

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/mitha-024/cloud-native-cicd-kubernetes.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME .'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f k8s/'
            }
        }
    }
}
