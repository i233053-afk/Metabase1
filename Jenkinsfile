pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building Metabase...'
                sh './gradlew build' // assuming Metabase uses Gradle
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh './gradlew test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying Metabase...'
                // optional deployment commands
            }
        }
    }
}
