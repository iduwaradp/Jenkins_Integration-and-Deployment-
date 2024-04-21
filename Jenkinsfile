pipeline {
    agent any

 //   environment {
  //  }

    stages {
        stage('Build') {
            steps {
                echo 'Building the code using Maven.' 
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit tests with JavaUnit...' 
                echo 'Running integration tests with Selenium...' 
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code quality with SonarQube...' 
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Scanning for vulnerabilities with SAST scanner..'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying application to staging server using AWS..'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment...'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying application to production server (e.g., using AWS tools)...'
            }
        }
    }

    // Post-build actions for email notifications (configure SMTP server details)
    post {
        success {
            emailaction(recipient: 'iduwaradp@gmail.com', 
                        subject: 'Pipeline Success - Build # ${currentBuild.number}', 
                        body: 'The pipeline has successfully completed all stages. Build logs are attached.', 
                        attachBuildLog: true)
        }
        failure {
            emailaction(recipient: 'iduwaradp@gmail.com', 
                        subject: 'Pipeline Failure - Build # ${currentBuild.number}', 
                        body: 'The pipeline has failed at stage ${currentStage.name}. Build logs are attached.', 
                        attachBuildLog: true)
        }
    }
}
