pipeline {
    agent any
    
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/BiteBuddy_Demo.git'  // Replace with your repository URL
            }
        }

        stage('Build') {
            steps {
                sh 'echo Building project...'  // Replace with your build command
            }
        }

        stage('Test') {
            steps {
                sh 'echo Running tests...'  // Replace with your test command
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo Deploying application...'  // Replace with your deploy command
            }
        }
    }
}
