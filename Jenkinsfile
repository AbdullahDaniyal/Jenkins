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
                sh 'npm install'
                
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
                
            }
        }

        stage('Test') {
            steps {
                echo 'Run tests...'
                
            }
        }

        stage('Docker Compose Up') {
            steps {
                echo 'Starting Docker Compose...'
                
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
}
