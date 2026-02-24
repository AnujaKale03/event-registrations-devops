pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/AnujaKale03/event-registrations-devops.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t event-registration-app .'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker run -d -p 5000:5000 event-registration-app'
            }
        }
    }
}