pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/i233053-afk/Metabase1.git'
            }
        }

        stage('Install Frontend Dependencies') {
            steps {
                sh '''
                    cd frontend
            npm install --legacy-peer-deps
                '''
            }
        }

        stage('Build Frontend') {
            steps {
                sh '''
                    cd frontend
            npm install --legacy-peer-deps
                '''
            }
        }
    }
}
