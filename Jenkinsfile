pipeline {
  agent any

  stages {

    stage('Install Firebase CLI') {
      steps {
        sh 'npm install -g firebase-tools'
      }
    }

    stage('Deploy') {
      steps {
        withCredentials([string(credentialsId: 'firebase_token', variable: 'TOKEN')]) {
          sh 'firebase deploy --project nourr-8ed30 --token "$TOKEN"'
        }
      }
    }
  }
}