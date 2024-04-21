pipeline {
    agent any

    environment {
        DIRECTORY_PATH = 'C:/Users/DELL/OneDrive/Desktop/deakin learning/sem 1/sit223'
        TESTING_ENVIRONMENT = 'testing_environment'
        PRODUCTION_ENVIRONMENT = "INDUWARA MUTHUGALA" 
    }

    stages {
        stage('Build') {
            steps {
                echo 'Fetching source code from the directory path specified by the environment variable.'

                echo 'Compiling the code and generating any necessary artifacts.'
            }
        }
        stage('Test') {
            steps {
                echo ' unit tests...'
                echo ' integration tests...'
            }
        }
        stage('Code Quality Check') {
            steps {
                echo 'Checking the quality of the code...'
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying the application to ${TESTING_ENVIRONMENT} ..."
            }
        }
        stage('Approval') {
            steps {
                echo 'Waiting for manual approval...'
                script{
                     sleep time: 10, unit: 'SECONDS'
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploying the code to ${PRODUCTION_ENVIRONMENT} environment..."
            }
        }
    }
}

