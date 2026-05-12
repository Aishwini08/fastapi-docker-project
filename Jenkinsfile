pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/Aishwini08/fastapi-docker-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t fastapi-app .'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker-compose up -d --build'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully! 🚀'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}