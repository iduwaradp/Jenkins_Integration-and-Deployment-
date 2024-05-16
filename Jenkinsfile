// // #!/usr/bin/env groovy

// // pipeline {
// //     agent any
    
// //     stages {
// //         stage('Build') {
// //             steps {
// //                 echo 'Building the code using Maven.' 
// //             }
// //         }
// //         stage('Unit and Integration Tests') {
// //             steps {
// //                 echo 'Running unit tests with JavaUnit...' 
// //                 echo 'Running integration tests with Selenium...' 
// //             }
// //         }
// //         stage('Code Analysis') {
// //             steps {
// //                 echo 'Analyzing code quality with SonarQube...' 
// //             }
// //         }
// //         stage('Security Scan') {
// //             steps {
// //                 echo 'Scanning for vulnerabilities with SAST scanner..'
// //             }
// //         }
// //         stage('Deploy to Staging') {
// //             steps {
// //                 echo 'Deploying application to staging server using AWS..'
// //             }
// //         }
// //         stage('Integration Tests on Staging') {
// //             steps {
// //                 echo 'Running integration tests on staging environment...'
// //             }
// //         }
// //         stage('Deploy to Production') {
// //             steps {
// //                 echo 'Deploying application to production server using AWS tools..'
// //             }
// //         }
// //     }
  
// //     post {
// //         success {
// //             emailext (
// //                 to: "testg3758@gmail.com",
// //                 subject: "Pipeline Success - Build # ${currentBuild.number}",
// //                 body: "The pipeline has successfully completed all stages. Build logs are attached.",
             
// //             )
// //         }
// //         failure {
// //             emailext (
// //                 to: "testg3758@gmail.com",
// //                 subject: "Pipeline Failure - Build # ${currentBuild.number}",
// //                 body: "The pipeline has failed at stage ${env.STAGE_NAME}. Build logs are attached.",
              
// //             )
// //         }
// //     }
// // }

// pipeline {
//     agent any
    
//     stages {
//         stage('Build') {
//             steps {
//                 echo 'Building the code using Maven.' 
//             }
//         }
//         stage('Unit and Integration Tests') {
//             steps {
//                 echo 'Running unit tests with JavaUnit...' 
//                 echo 'Running integration tests with Selenium...' 
//             }
//         }
//         stage('Code Analysis') {
//             steps {
//                 echo 'Analyzing code quality with SonarQube...' 
//             }
//         }
//         stage('Security Scan') {
//             steps {
//                 echo 'Scanning for vulnerabilities with SAST scanner..'
//             }
//         }
//         stage('Deploy to Staging') {
//             steps {
//                 echo 'Deploying application to staging server using AWS..'
//             }
//         }
//         stage('Integration Tests on Staging') {
//             steps {
//                 echo 'Running integration tests on staging environment...'
//             }
//         }
//         stage('Deploy to Production') {
//             steps {
//                 echo 'Deploying application to production server using AWS tools..'
//             }
//         }
//     }
  
//     post {
//         success {
//             mail to: "testg3758@gmail.com",
//                  subject: "Pipeline Success - Build # ${currentBuild.number}",
//                  body: "The pipeline has successfully completed all stages. Build logs are attached."
//         }
//         failure {
//             mail to: "testg3758@gmail.com",
//                  subject: "Pipeline Failure - Build # ${currentBuild.number}",
//                  body: "The pipeline has failed at stage ${currentStage.name}. Build logs are attached."
//         }
//     }
// }


pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Example: Build a Java project using Maven
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                // Example: Run automated tests using JUnit
                sh 'mvn test'
            }
        }
        stage('Code Quality Analysis') {
            steps {
                // Example: Run code analysis using SonarQube scanner
                withSonarQubeEnv('SonarQube') {
                    sh 'mvn sonar:sonar'
                }
            }
        }
        stage('Deploy') {
            steps {
                // Example: Deploy application to a Docker container
                sh 'docker-compose up -d'
            }
        }
        stage('Release') {
            steps {
                // Example: Promote application to production environment
                sh 'octo deploy-release'
            }
        }
        stage('Monitoring and Alerting') {
            steps {
                // Example: Monitor application using Datadog
                sh 'datadog-monitor'
            }
        }
    }
}



