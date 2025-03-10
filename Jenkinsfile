pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                script {
                    git branch: 'main', url: 'https://github.com/Gigachadicus/pes1ug22am164_jenkins.git'
                }
            }
        }

        stage('Build') {
            steps {
                echo 'Building the C++ application...'
                sh 'g++ -o pes1ug22am164 hello.cpp'  // Compile main.cpp as pes1ug22am164
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'chmod +x pes1ug22am164'  // Ensure executable permission
                sh './pes1ug22am164'  // Execute the compiled binary
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                sh 'echo "Deployment successful"'  // Placeholder for real deployment steps
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
