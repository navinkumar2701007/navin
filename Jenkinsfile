pipeline {
    agent any

    stages {
        stage('Deploy to NGINX Server') {
            steps {
                sshagent(['nginx-ssh']) {
                    sh '''
                    ssh -o StrictHostKeyChecking=no ubuntu@172.31.10.221 \
                    "sudo rm -rf /var/www/app/*"

                    scp -o StrictHostKeyChecking=no -r * \
                    ubuntu@172.31.10.221:/var/www/app/
                    '''
                }
            }
        }
    }
}
