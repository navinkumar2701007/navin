pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/navinkumar2701007/navin.git'
            }
        }

        stage('Deploy to NGINX Server') {
            steps {
                sshagent(['nginx-ssh']) {

                    sh 'ssh -o StrictHostKeyChecking=no ubuntu@15.207.88.84 sudo rm -rf /var/www/portfolio/*'

                    sh 'scp -o StrictHostKeyChecking=no -r * ubuntu@15.207.88.84:/var/www/portfolio/

                    sh 'ssh ubuntu@15.207.88.84 sudo systemctl restart nginx'
                }
            }
        }
    }
}

