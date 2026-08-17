pipeline {
    // Defines where the automation will execute (any available runner/node)
    agent any 

    stages {
        stage('Build') {
            steps {
                echo 'Building your application...'
                // Example: sh 'mvn clean package' (for Java apps)
            }
        }
        
        stage('Test') {
            steps {
                echo 'Running unit tests...'
                // Example: sh 'npm test' (for NodeJs apps)
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying to the server...'
                // Example: sh './deploy.sh'
            }
        }
    }
    
    
    post {
        always {
            echo 'Pipeline has finished executing.'
        }
        success {
            echo 'The build was successful!'
        }
        failure {
            echo 'The build failed. Please check the logs.'
        }
    }
}