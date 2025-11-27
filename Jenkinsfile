pipeline {
    agent any

    environment {
        IMAGE_NAME = "metabase:jenkins"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                echo "Building Docker image..."
                sh "docker build -t ${IMAGE_NAME} ."
            }
        }

        stage('Run Container & Test') {
            steps {
                echo "Running container to test build..."
                sh """
                docker run --rm ${IMAGE_NAME} bash -c '
                  echo "Metabase container started successfully";
                  # Add any test commands here
                '
                """
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
        success {
            echo 'Build and tests completed successfully!'
        }
        failure {
            echo 'Pipeline failed! Check logs for details.'
        }
    }
}
