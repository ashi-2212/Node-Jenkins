pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                echo 'Cloning repository...'
                git 'https://github.com/ashi-2212/Node-Jenkins-sample.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies...'
                sh 'npm install'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                sh 'node index.js &'  // Run the application in the background
            }
        }
        stage('Verify Application') {
            steps {
                echo 'Verifying application...'
                sh 'curl http://16.171.233.245:3000'  
            }
        }
    }
    post {
        success {
            echo 'Deployment successful!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}
