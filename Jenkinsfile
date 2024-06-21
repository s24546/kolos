pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/s24546/kolos.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Run Tests') {
            steps {
                sh 'npm test'
            }
        }
        stage('Static Code Analysis') {
            steps {
                sh 'npm run lint'
            }
        }
    }
    post {
        always {
            junit 'test-results.xml'
        }
    }
}