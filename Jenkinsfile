pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t event-registration-app .'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker stop event-registration-app || exit 0'
                bat 'docker rm event-registration-app || exit 0'
                bat 'docker run -d --name event-registration-app -p 5000:5000 event-registration-app'
            }
        }
    }
}