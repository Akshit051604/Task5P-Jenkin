pipeline {
    agent any

    environment {
        DIRECTORY_PATH = "/path/to/source/code"
        TESTING_ENVIRONMENT = "Netlify"
        PRODUCTION_ENVIRONMENT = "Akshit Goyal"
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
                success {
                    mail to: "baren.zemo02@gmail.com",
                        body: "The Test stage has completed. Check logs for details."
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
                    mail to: "baren.zemo02@gmail.com"
                             body: "The Security Scan stage has completed. Check logs for details."
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
