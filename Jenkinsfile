pipeline {
    agent any
    
    environment {
        // Define any environment variables you need here
        MAVEN_HOME = tool name: 'Maven 3.8.6', type: 'maven'
    }
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from GitHub
                git url: 'https://github.com/Panku51/Whiz_repo.git', branch: 'main'
            }
        }
        
        stage('Build') {
            steps {
                // Build the application using Maven
                script {
                    sh "${MAVEN_HOME}/bin/mvn clean package"
                }
            }
        }
        
        stage('Test') {
            steps {
                // Run tests
                script {
                    sh "${MAVEN_HOME}/bin/mvn test"
                }
            }
        }
        
        stage('Deploy') {
            steps {
                // Deploy the application - this step will vary based on your deployment method
                echo 'Deploying the application...'
                // Example: Deploy to an artifact repository, or perform deployment tasks
                // sh 'deploy.sh' // Replace with actual deploy script or commands
            }
        }
    }
    
    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build or deployment failed!'
        }
    }
}
