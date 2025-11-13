stage('Deploy to NGINX Server') {
    sshagent(['ubuntu']) {
        sh """
            ssh -o StrictHostKeyChecking=no ubuntu@15.207.88.84 sudo rm -rf /var/www/portfolio/*
            scp -o StrictHostKeyChecking=no -r * ubuntu@15.207.88.84:/var/www/portfolio/
            ssh -o StrictHostKeyChecking=no ubuntu@15.207.88.84 sudo systemctl restart nginx
        """
    }
}

