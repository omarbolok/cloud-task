pipeline {
    agent any

    tools {
        nodejs "node16"
    }

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