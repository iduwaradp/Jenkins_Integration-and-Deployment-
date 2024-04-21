pipeline {
    agent any

 //   environment {
  //  }

    stages {
        stage('Build') {
            steps {
                echo 'Dependacy Instrallation...' 
                echo 'Building the application..' 
                git branch: 'main',url: 'https://github.com/iduwaradp/Jenkins_Integration-and-Deployment-.git'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit tests with JavaUnit...' 
               script{
                   def emailScript - """
                   \$SMTPServer - "stmp.gmail.com"
                    \$SMTPFrom -"iduwaradp@gmail.com"
                     \$SMTPTo -"iduwaradp@gmail.com"
                      \$SMTPSubject - "Test passed"
                       \$SMTPBody - "The test phase has passed"
                        \$SMTPUsername -"iduwaradp@gmail.com"
                         \$SMTPassword -
                         
                         Send-MaliMassage -From \$SMTPFrom -To \$SMTPTo -Subject \$SMTPSubject -Body \$SMTPBody -SmtpServer  \$SMTPServer
                         """
                         powershwll(emailscript)
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
                
                script{
                   def emailScript - """
                   \$SMTPServer - "stmp.gmail.com"
                    \$SMTPFrom -"iduwaradp@gmail.com"
                     \$SMTPTo -"iduwaradp@gmail.com"
                      \$SMTPSubject - "Test passed"
                       \$SMTPBody - "The test phase has passed"
                        \$SMTPUsername -"iduwaradp@gmail.com"
                         \$SMTPassword -
                         
                         Send-MaliMassage -From \$SMTPFrom -To \$SMTPTo -Subject \$SMTPSubject -Body \$SMTPBody -SmtpServer  \$SMTPServer
                         """
                         powershwll(emailscript)
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
                echo 'Deploying application to production server using AWS tools....'
            }
        }
    }

   // Post-build actions for email notifications (configure SMTP server details)
    post {
        success {
            emailext subject: 'Pipeline Failure - Build # ${currentBuild.number}', 
                        body: 'The pipeline has failed at stage ${currentStage.name}. Build logs are attached.', 
                        to: 'iduwaradp@gmail.com', 
                        attachBuildLog: true
        }
        failure {
            emailext subject: 'Pipeline Failure - Build # ${currentBuild.number}', 
                        body: 'The pipeline has failed at stage ${currentStage.name}. Build logs are attached.', 
                        to: 'iduwaradp@gmail.com', 
                        attachBuildLog: true
        }
     }
}
