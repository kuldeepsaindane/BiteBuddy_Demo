pipeline {
    agent any

    environment {
        REPO_URL = 'https://github.com/kuldeepsaindane/BiteBuddy_Demo.git'  // Replace with your repo URL
    }

    stages {
        stage('Checkout Repository') {
            steps {
                // Clone the repository
                git url: "$REPO_URL", branch: 'main'  // Replace with your branch if necessary
            }
        }

        stage('Install Nginx') {
            steps {
                // Install Nginx on the agent (if necessary)
                sh 'sudo apt update -y && sudo apt install -y nginx'
            }
        }

        stage('Copy index.html to Web Directory') {
            steps {
                // Copy the index.html file to the Nginx root directory
                sh 'sudo cp index.html /var/www/html/index.html'
            }
        }

        stage('Start Nginx Server') {
            steps {
                // Start Nginx server
                sh 'sudo systemctl start nginx'
                // Ensure Nginx is enabled to start on boot
                sh 'sudo systemctl enable nginx'
            }
        }
    }
}
