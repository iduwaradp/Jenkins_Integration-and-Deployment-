pipeline {
    agent any 
    stages {
        stage('Build') {
            steps {
                // No build step needed for HTML/CSS
                echo 'Building HTML/CSS project' 
            }
        }
        stage('Test') {
            steps {
                // Run tests (e.g., using a testing framework like Cypress)
                echo 'Running tests' 
            }
        }
        stage('Deploy') {
            steps {
                // Deploy to a web server (e.g., using a script or a tool like rsync)
                echo 'Deploying to test server' 
            }
        }
    }
}

