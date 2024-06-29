pipeline {
    agent any
    environment {
        FIREBASE_DEPLOY_TOKEN = credentials('firebase-token')
    }
        stages {
           stage('Building') {
            steps {
                sh 'firebase --version'
            }
         }

          stage('Testing Env') {
            steps {
                sh 'firebase deploy -P testing-env-denvet --token "$FIREBASE_DEPLOY_TOKEN"'
                //Añadir testing
                //Usar SELENIUM para automation testing
            }
         }

        stage('Staging Env') {
            steps {
                 sh 'firebase deploy -P staging-env-devnet --token "$FIREBASE_DEPLOY_TOKEN"'
            }
        }

        stage('Production Env') {
            steps {
                sh 'firebase deploy -P production-env-devnet --token "$FIREBASE_DEPLOY_TOKEN"'    
            }
        }
    }
}
