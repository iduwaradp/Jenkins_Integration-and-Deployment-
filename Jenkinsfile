pipeline {
    agent any 
    stages {
        stage('Build') {
            steps {
                checkout scm 
                sh 'mvn clean package'
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Code Quality Analysis') {
            steps {
                sh 'mvn sonar:sonar' 
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker build -t my-app:latest .'
                sh 'docker-compose up -d'
            }
        }
        stage('Release') {
            steps {
                sh 'aws codedeploy deploy'
            }
        }
        stage('Monitoring and Alerting') {
            steps {
                // Datadog configuration
            }
        }
    }
}
