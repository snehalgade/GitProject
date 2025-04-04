pipeline {
    agent any  // Runs on any available Jenkins node

    environment {
        APP_VERSION = "1.0"  // Define environment variables
    }

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'master', url: 'https://github.com/snehalgade/GitProject.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'  // Runs Maven build
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'  // Runs unit tests
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying version ${APP_VERSION}..."  
                // Add deployment commands here (Docker, Kubernetes, SCP, etc.)
            }
        }
    }

    post {
        success { echo '✅ Build Successful!' }
        failure { echo '❌ Build Failed!' }
    }
}
