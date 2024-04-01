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
                echo 'npm install'
                
            }
        }

        stage('Build') {
            steps {
                echo 'npm run build'
                
            }
        }

        stage('Test') {
            steps {
                echo 'Run tests...'
                
            }
        }

        stage('Docker Compose Up') {
            steps {
                sh 'sleep 2m'
                
                echo 'docker compose up -d'
            }
        }
        
        stage('Cleanup') {
            steps {
                echo 'Shutting down Docker Compose...'
                echo 'docker compose down'
            }
        }
    }
}
