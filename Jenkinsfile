pipeline {
    // Defines where the automation will execute (any available runner/node)
    agent {
        label 'Roboshop'
    }
    environment {
        name = "Manoj"
    }
    options {
        disableConcurrentBuilds()
        timestamps()
        timeout(time: 10, unit: 'MINUTES')
    }

    parameters {
        string(name: 'VERSION', defaultValue: '1.0', description: 'Enter application version')
        
        choice(name: 'ENVIRONMENT', choices: ['dev', 'qa', 'prod'], description: 'Select environment')

        booleanParam(name: 'RUN_TESTS', defaultValue: true, description: 'Run tests?')

        password( name: 'PASSWORD', defaultValue: '', description: 'Enter password')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building your application...'
                echo "My name is ${name}"
                sleep 5
                // Example: sh 'mvn clean package' (for Java apps)
            }
        }
        
        stage('Test') {
            steps {
                echo 'Running unit tests... with agent'
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