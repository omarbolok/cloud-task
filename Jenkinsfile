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
                withCredentials([
                    file(
                        credentialsId: 'gcp-key',
                        variable: 'GOOGLE_APPLICATION_CREDENTIALS'
                    )
                ]) {
                    sh '''
                        export GOOGLE_APPLICATION_CREDENTIALS=$GOOGLE_APPLICATION_CREDENTIALS
                        firebase deploy --project nourr-8ed30
                    '''
                }
            }
        }
    }
}
