pipeline {
    agent { label 'nginx' }

    stages {
        stage('Deploy Frontend') {
            steps {
                sh '''
                cd /var/www/frontend
                git pull origin main
                '''
            }
        }
    }
}
