pipeline {
    agent any
    
    environment {
        // Define environment variables if needed
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/NaseemKhan005/react-bank-app'
            }
        }

        stage('Dependency Installation') {
            steps {
                // Assuming a structure where frontend dependencies need to be installed
                dir('path/to/frontend') { // Update with the actual path to your frontend within the repo
                    sh 'npm install'
                }
                // Add backend dependencies installation if needed
            }
        }

        stage('Build') {
            steps {
                // Assuming React frontend build script
                dir('path/to/frontend') { // Update with the actual path to your frontend within the repo
                    sh 'npm run build'
                }
                // Add backend build steps if needed
            }
        }

        stage('Test') {
            steps {
                // Add commands to run your tests. Example for a React application:
                dir('path/to/frontend') { // Update with the actual path to your frontend within the repo
                    sh 'npm test'
                }
                // Add backend testing steps if needed
            }
        }

        stage('Docker Compose Up') {
            steps {
                // Ensure docker daemon is accessible and docker-compose.yml is set up correctly
                // Note: Make sure Jenkins has permissions to execute Docker commands
                sh "docker compose up -d" // '-d' to run containers in the background
            }
        }
        
        stage('kill') {
            steps {
                sh "docker compose down"
            }
        }
    }
    post {
        always {
            // Clean up actions, like sending notifications or cleanup workspace
        }
        success {
            // Actions to perform on success
        }
        failure {
            // Actions to perform on failure
        }
    }
}
