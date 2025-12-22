pipeline {
    agent { label 'nginx' }

    stages {
        stage('Verify Agent') {
            steps {
                sh '''
                echo "Running on:"
                hostname
                whoami
                '''
            }
        }

        stage('Checkout Repo') {
            steps {
                sh '''
                rm -rf site
                git clone git@github.com:navinkumar2701007/navin.git site
                '''
            }
        }

        stage('Deploy Static Site') {
            steps {
                sh '''
                sudo rm -rf /var/www/navin/*
                sudo cp -r site/* /var/www/navin/
                '''
            }
        }

        stage('Reload NGINX') {
            steps {
                sh 'sudo systemctl reload nginx'
            }
        }
    }
}

