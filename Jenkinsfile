pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/AbdullahDaniyal/Jenkins.git'
            }
        }

        stage('Dependency Installation') {
            steps {
                echo 'Install dependencies...'
                // Add actual dependency installation commands here
            }
        }

        stage('Build') {
            steps {
                echo 'Build the project...'
                // Add actual build commands here
            }
        }

        stage('Test') {
            steps {
                echo 'Run tests...'
                // Add actual test commands here
            }
        }

        stage('Docker Compose Up') {
            steps {
                echo 'Starting Docker Compose...'
                // Make sure Jenkins has permissions to run Docker commands
                sh 'docker compose up -d'
            }
        }
        
        stage('Cleanup') {
            steps {
                echo 'Shutting down Docker Compose...'
                sh 'docker compose down'
            }
        }
    }
    post {
        always {
            echo 'This will always run regardless of the result.'
        }
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
