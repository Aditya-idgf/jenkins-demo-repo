
pipeline {
    agent any

    environment {
        REPO_URL = 'https://github.com/Aditya-idgf/jenkins-demo-repo.git'
        BRANCH = 'main'
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Cloning repository from GitHub...'
                git branch: "${BRANCH}",
                    url: "${REPO_URL}",
                    credentialsId: 'github-pat-credentials'
            }
        }

        stage('Build') {
            steps {
                echo 'Building application...'
                bat 'echo Build step executed'
            }
        }

        stage('Test') {
            steps {
                echo 'Running unit tests...'
                bat 'echo Test step executed'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying to staging server...'
                bat 'echo Deploy step executed'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully.'
        }
        failure {
            echo 'Pipeline failed. Check console output.'
        }
    }
}
