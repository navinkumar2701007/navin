pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/navinkumar2701007/navin.git'
            }
        }

        stage('Deploy to NGINX Server') {
            steps {
                sshagent(['ubuntu']) {
                    sh """
                        ssh -o StrictHostKeyChecking=no ubuntu@15.207.88.84 sudo rm -rf /var/www/portfolio/*
                        scp -o StrictHostKeyChecking=no -r * ubuntu@15.207.88.84:/var/www/portfolio/
                        ssh -o StrictHostKeyChecking=no ubuntu@15.207.88.84 sudo systemctl restart nginx
                    """
                }
            }
        }
    }
}

