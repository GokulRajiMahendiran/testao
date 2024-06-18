pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                script {
                    // Ensure Node.js and npm are installed on your Jenkins agent
                    sh 'npm install'
                }
            }
        }
        
        stage('Build Project') {
            steps {
                script {
                    sh 'npm run build'
                }
            }
        }
    }
}
