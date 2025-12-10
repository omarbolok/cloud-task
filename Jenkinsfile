pipeline {
    agent any

    stages {
        stage('Deploy to Firebase') {
            steps {
                sh 'firebase deploy --token $firebase_token'
            }
        }
    }
}