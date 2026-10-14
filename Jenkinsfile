pipeline {
    agent any

    triggers {
        pollSCM('H/5 * * * *')
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/pateldeep3108/morning_devops.git'
            }
        }

        stage('Deploy Website') {
            steps {
                sh '''
                    echo "Deploying website..."
                    sudo rsync -av --exclude='.git' ./ /var/www/html/
                    echo "Deployment completed"
                '''
            }
        }
    }
}
