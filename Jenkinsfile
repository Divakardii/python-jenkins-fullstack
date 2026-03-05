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
 sh '''
 cd backend
 nohup python3 app.py > app.log 2>&1 &
 '''
 }
 }

 stage('Deploy Frontend') {
 steps {
 sh 'sudo cp frontend/index.html /var/www/html/'
 }
 }

 }

}
