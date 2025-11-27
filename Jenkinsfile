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
                sh 'docker build -t metabase .'
                
                // Optionally, run tests
                sh 'docker run --rm metabase bash -c "echo Run tests here if needed"'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}
