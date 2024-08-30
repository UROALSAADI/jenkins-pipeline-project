pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                // Example: sh 'mvn clean package'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Testing...'
                // Example: sh 'mvn test'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code...'
                // Example: sh 'sonar-scanner'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Scanning for security vulnerabilities...'
                // Example: sh 'owasp-dependency-check'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging...'
                // Example: sh 'deploy-to-staging.sh'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
                // Example: sh 'run-integration-tests.sh'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production...'
                // Example: sh 'deploy-to-production.sh'
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
