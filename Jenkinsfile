pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main',
                    url: 'git@github.com:akhiltm18/myweb.git'
            }
        }

        stage('Build') {
            steps {
                echo "Build step (if needed)"
                // npm install / mvn package / etc
            }
        }

        stage('Deploy to Web Server') {
            steps {
                sh '''
                rsync -avz --delete \
                ./ ubuntu@172.31.22.202:/var/www/html/
                '''
            }
        }
    }
}
