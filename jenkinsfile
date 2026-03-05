pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/Divakardii/python-jenkins-fullstack.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip3 install -r backend/requirements.txt'
            }
        }

        stage('Run Backend') {
            steps {
                sh 'nohup python3 backend/app.py &'
            }
        }

        stage('Deploy Frontend') {
            steps {
                sh 'sudo cp frontend/index.html /var/www/html/'
            }
        }

    }
}
