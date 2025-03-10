pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                script {
                    checkout scm
                }
            }
        }
        stage('Build') {
            steps {
                echo 'Building the C++ application...'
                sh 'make -C main'  // This will use the Makefile in the main directory
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'cd main && chmod +x hello_exec'  // Ensure executable permission
                sh 'cd main && ./hello_exec'  // Execute the compiled binary
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                sh 'echo "Deployment successful for PES1UG22AM164"'  // Placeholder for real deployment steps
            }
        }
    }
    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed'
        }
    }
}
