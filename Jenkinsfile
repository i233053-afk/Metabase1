pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Set up Java') {
            steps {
                // Java 17 setup on Jenkins agent
                sh 'java -version || sudo apt-get install openjdk-17-jdk -y'
            }
        }

        stage('Build') {
            steps {
                sh './gradlew build -x test'
            }
        }

        stage('Test') {
            steps {
                sh './gradlew test'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}
