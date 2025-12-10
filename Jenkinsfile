pipeline {
  agent any

  tools {
    nodejs "node16"  
  }

  stages {
    stage('Install Firebase CLI') {
      steps {
        sh 'npm install -g firebase-tools'
      }
    }

    stage('Deploy') {
      steps {
        withCredentials([string(credentialsId: 'FIREBASE_TOKEN', variable: 'TOKEN')]) {
          sh 'firebase deploy --project nourr-8ed30 --token "$TOKEN"'
        }
      }
    }
  }
}