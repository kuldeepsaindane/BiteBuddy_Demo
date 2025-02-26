pipeline {
    agent any

    environment {
        REPO_URL = 'https://github.com/kuldeepsaindane/BiteBuddy_Demo.git'
    }

    stages {
        stage('Checkout Repository') {
            steps {
                git url: "$REPO_URL", branch: 'main'
            }
        }

        stage('Install Nginx') {
            steps {
                // Install Nginx without using sudo if Jenkins has root privileges
                sh 'apt update -y && apt install -y nginx'
            }
        }

        stage('Copy index.html to Web Directory') {
            steps {
                // Ensure the correct permissions are set for the directory
                sh 'cp index.html /var/www/html/index.html'
                sh 'chown -R ubuntu:ubuntu /var/www/html'
            }
        }

        stage('Start Nginx Server') {
            steps {
                // Restart Nginx service without using sudo if Jenkins has root privileges
                sh 'systemctl restart nginx'
            }
        }
    }
}
