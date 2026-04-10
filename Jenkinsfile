pipeline {
    agent any

    environment {
        IMAGE_NAME = "pravinukunde/ai-static-site"
    }

    stages {

        stage('Checkout') {
            steps {
                echo "Pulling code from GitHub..."
                git branch: 'main', url: 'https://github.com/pravinukunde7/ai-vision-website.git'
            }
        }

        stage('Build') {
            steps {
                echo "Building Docker image..."
                sh 'docker build -t $IMAGE_NAME .'
            }
        }

        stage('Test') {
            steps {
                echo "Running basic test..."
                sh 'echo "Test Passed"'
            }
        }

        stage('Push Image') {
            steps {
                echo "Pushing image to DockerHub..."
                withCredentials([usernamePassword(credentialsId: 'dockerhub-creds', usernameVariable: 'USER', passwordVariable: 'PASS')]) {
                    sh '''
                    echo $PASS | docker login -u $USER --password-stdin
                    docker push $IMAGE_NAME
                    '''
                }
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying container..."
                sh '''
                docker stop ai-app || true
                docker rm ai-app || true
                docker run -d -p 3000:80 --name ai-app $IMAGE_NAME
                '''
            }
        }
    }
}
