pipeline {
    agent any
    stages {
        stage('Setup') {
            steps{
                echo 'Installing dependencies...'
                bat 'python -m pip install -r requirements.txt'
            }
        }
        stage('Build & Test') {
            steps {
                echo 'Running ML pipleline...'
                bat 'python ml_pipleline.py'
            }
        }
    }
    post {
        success {
            echo 'Pipleline SUCCESS - Model validated'
        }
        failure {
            echo 'Pipleline FAILED - Check logs'
        }
    }
}
