// Jenkinsfile

pipeline {
    // Replace 'Maven_3.8.6' with the name you configured for Maven in Step 1.
    agent any

    tools {
        maven 'Maven_3.8.6' 
    }

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Cloning the GitHub repository...' 
            }
        }

        stage('Build & Test') {
            steps {
                sh 'mvn -B clean install'
            }
        }

        stage('Publish Test Results') {
            steps {
                junit 'target/surefire-reports/*.xml'
            }
        }
    }

    post {
        success {
            echo 'Build and Tests completed successfully!'
        }
        failure {
            echo 'One or more tests failed. Check the test results report.'
        }
    }
}