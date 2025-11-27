pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/i233053-afk/Metabase1.git'
            }
        }

        stage('Install Backend Dependencies') {
            steps {
                sh '''
                    cd src/metabase
                    lein deps
                '''
            }
        }

        stage('Build Backend JAR') {
            steps {
                sh '''
                    cd src/metabase
                    lein uberjar
                '''
            }
        }

        stage('Install Frontend Dependencies') {
            steps {
                sh '''
                    cd frontend
                    npm install
                '''
            }
        }

        stage('Build Frontend') {
            steps {
                sh '''
                    cd frontend
                    npm run build
                '''
            }
        }
    }
}
