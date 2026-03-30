pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "ahmed277/python-devsecops"
        VERSION = "v1"
    }

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/ahmedessam1197/DevSecOps-Python-Microservices-Platform.git'            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $DOCKER_IMAGE:$VERSION -f Docker/Dockerfile .'
            }
        }

        stage('Trivy Security Scan') {
            steps {
                sh 'trivy image $DOCKER_IMAGE:$VERSION'
            }
        }

        stage('Push Image') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub',
                    usernameVariable: 'USER',
                    passwordVariable: 'PASS'
                )]) {

                    sh 'echo $PASS | docker login -u $USER --password-stdin'
                    sh 'docker push $DOCKER_IMAGE:$VERSION'
                }
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f k8s/'
            }
        }

    }
}