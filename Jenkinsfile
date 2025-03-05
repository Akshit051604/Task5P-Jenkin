pipeline {
    agent any

    environment {
        DIRECTORY_PATH = "/path/to/source/code"
        TESTING_ENVIRONMENT = "Netlify"
        PRODUCTION_ENVIRONMENT = "Akshit Goyal"
        EMAIL_RECIPIENTS = "baren.zemo02@gmail.com"
    }

    stages {
        stage('Build') {
            steps {
                echo "Fetching the source code from ${DIRECTORY_PATH}"
                echo "Compiling the code and generating artifacts"
                echo "hello"
            }
        }

        stage('Test') {
            steps {
                echo "Running unit tests"
                echo "Running integration tests"
            }
            post {
                always {
                    emailext subject: "Jenkins: Test Stage - Completed",
                             body: "The Test stage has completed. Check logs for details.",
                             attachLog: true,
                             to: EMAIL_RECIPIENTS
                }
            }
        }

        stage('Code Quality Check') {
            steps {
                echo "Performing code quality check"
            }
        }

        stage('Security Scan') {
            steps {
                echo "Performing security scan on the code"
                echo "Identifying vulnerabilities (simulated)"
                echo "Security scan completed"
            }
            post {
                always {
                    emailext subject: "Jenkins: Security Scan - Completed",
                             body: "The Security Scan stage has completed. Check logs for details.",
                             attachLog: true,
                             to: EMAIL_RECIPIENTS
                }
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying the application to ${TESTING_ENVIRONMENT}"
            }
        }

        stage('Approval') {
            steps {
                echo "Waiting for approval..."
                sleep(time: 10, unit: 'SECONDS')
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Deploying the application to ${PRODUCTION_ENVIRONMENT}"
            }
        }
    }
}
