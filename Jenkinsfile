

pipeline {
    agent any
    
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
                script {
                    def emailScript = """
                    \$SMTPServer = "stmp.gmail.com"
                    \$SMTPFrom = "testg3758@gmail.com"
                    \$SMTPTo = "testg3758@gmail.com"
                    \$SMTPSubject = "Test passed"
                    \$SMTPBody = "The test phase has passed"
                    \$SMTPUsername = "testg3758@gmail.com"
                    \$SMTPassword = "fcvw urli aslv egui"
                    
                    Send-MailMessage -From \$SMTPFrom -To \$SMTPTo -Subject \$SMTPSubject -Body \$SMTPBody -SmtpServer \$SMTPServer
                    """
                    powershell(emailScript)
                }
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
                script {
                    def emailScript = """
                    \$SMTPServer = "stmp.gmail.com"
                    \$SMTPFrom = "testg3758@gmail.com"
                    \$SMTPTo = "testg3758@gmail.com"
                    \$SMTPSubject = "Test passed"
                    \$SMTPBody = "The test phase has passed"
                    \$SMTPUsername = "testg3758@gmail.com"
                    \$SMTPassword = "fcvw urli aslv egui"
                    
                    Send-MailMessage -From \$SMTPFrom -To \$SMTPTo -Subject \$SMTPSubject -Body \$SMTPBody -SmtpServer \$SMTPServer
                    """
                    powershell(emailScript)
                }
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
                echo 'Deploying application to production server using AWS tools..'
            }
        }
    }
  
    post {
        success {
            emailext attachLog: true, body: 'The pipeline has successfully completed all stages. Build logs are attached.', replyTo: 'testg3758@gmail.com', subject: 'Pipeline Success - Build # ${currentBuild.number}', to: 'testg3758@gmail.com'
        }
        failure {
            emailext attachLog: true, body: 'The pipeline has failed at stage ${currentStage.name}. Build logs are attached.', replyTo: 'testg3758@gmail.com', subject: 'Pipeline Failure - Build # ${currentBuild.number}', to: 'testg3758@gmail.com'
        }
    }
}
