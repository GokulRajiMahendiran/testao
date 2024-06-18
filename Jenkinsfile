pipeline {
    agent any
    
    environment {
        // Define any environment variables here
      //   NODE_ENV = 'production'
    }
    
    stages {
        stage('Checkout') {
            steps {
                // Check out the code from the current branch
                checkout scm
            }
        }
        
        stage('Install Dependencies') {
            steps {
                // Install npm dependencies
                script {
                    if (fileExists('package-lock.json')) {
                        sh 'npm ci'
                    } else {
                        sh 'npm install'
                    }
                }
            }
        }
        
        stage('Build') {
            steps {
                // Run your build commands here
                sh 'npm run build'
            }
        }
        
        
    }
    
    post {
        always {
            // Actions to perform regardless of build result
            echo 'Cleaning up...'
            cleanWs()
        }
        
        success {
            // Actions to perform if the build succeeds
            echo 'Build succeeded!'
        }
        
        failure {
            // Actions to perform if the build fails
            echo 'Build failed!'
        }
    }
}
