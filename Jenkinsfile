pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build & Test') {
            steps {
                // Build using Docker (recommended for Metabase)
                sh 'sudo docker build -t metabase .'
                
                // Optionally, run tests
                sh 'sudo docker run --rm metabase bash -c "echo Run tests here if needed"'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}
