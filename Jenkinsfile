pipeline {
    agent any

    environment {
        // Define environment variables here if needed
        // Example: DIRECTORY_PATH = '/path/to/code'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
                // Example command using Maven
                sh 'mvn clean package'
                // If you use Gradle instead of Maven, you could use: sh 'gradle build'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit tests...'
                // Example command for unit tests using Maven
                sh 'mvn test'
                // Integration tests could be added here or in a separate step
                echo 'Running integration tests...'
                // Example command for integration tests
                // sh 'run-integration-tests.sh'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Analyzing code with SonarQube...'
                // Example command for SonarQube analysis
                sh 'sonar-scanner'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Scanning for security vulnerabilities...'
                // Example command for OWASP Dependency-Check
                sh 'dependency-check.sh --project MyProject'
                // Alternatively, use Snyk if preferred
                // sh 'snyk test'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging environment...'
                // Example command for deployment to staging using AWS CLI
                sh 'aws deploy push --application-name MyApp --s3-location s3://mybucket/myapp.zip'
                // Or use Jenkins built-in deployment plugin
                // sh 'deploy-to-staging.sh'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment...'
                // Example command for integration tests using Selenium
                // sh 'run-integration-tests.sh'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production environment...'
                // Example command for deployment to production using AWS CLI
                sh 'aws deploy push --application-name MyApp --s3-location s3://mybucket/myapp.zip'
                // Or use Jenkins deployment plugin
                // sh 'deploy-to-production.sh'
            }
        }
    }

    post {
        success {
            mail to: 'yaseralsaadi132@gmail.com',
                 subject: "Pipeline succeeded",
                 body: "The pipeline has successfully completed."
        }
        failure {
            mail to: 'yaseralsaadi132@gmail.com',
                 subject: "Pipeline failed",
                 body: "The pipeline has failed. Please check the logs."
        }
    }
}
