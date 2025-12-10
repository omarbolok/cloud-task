pipeline {
    agent any

    stages {
        stage('Install deps') {
            steps {
                sh 'npm install'
            }
        }
        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
        stage('Deploy to Firebase') {
            steps {
                sh 'firebase deploy --token $firebase_token'
            }
        }
    }
}