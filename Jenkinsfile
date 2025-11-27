pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/i233053-afk/Metabase1.git'
            }
        }

        stage('Install Backend Dependencies') {
            steps {
                sh 'lein deps'
            }
        }

        stage('Install Frontend Dependencies') {
            steps {
                sh 'yarn install'
            }
        }

        stage('Build Frontend') {
            steps {
                sh 'yarn build'
            }
        }

        stage('Build Backend JAR') {
            steps {
                sh 'lein uberjar'
            }
        }
    }
}
