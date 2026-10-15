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
            set -e
            echo "Deploying website..."
            sudo /usr/bin/rsync -av \
                --exclude='.git' \
                "$WORKSPACE/" /var/www/html/
            echo "Deployment completed"
        '''
    }
}
    }
}
