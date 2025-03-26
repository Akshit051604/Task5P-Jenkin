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
                echo "Fetching the source code from ${DIRECTORY_PATH} using Git"
                echo "Installing dependencies using npm install"
                echo "Compiling the code using Webpack/Babel"
                echo "Generating build artifacts in dist/ directory"
                echo "Running npm build command to create optimized production files"
            }
        }

        stage('Test') {
            steps {
                echo "Running unit tests using Jest/Mocha"
                echo "Running integration tests using Selenium/Cypress"
                echo "Generating test reports and storing in /test-reports"
                echo "Running npm test to validate application functionality"
            }
            post {
                success {
                    mail(to: "baren.zemo02@gmail.com",
                         subject: "Test Stage Completed",
                         body: "The Test stage has completed. Check logs for details.")
                }
            }
        }

        stage('Code Quality Check') {
            steps {
                echo "Performing static code analysis using ESLint/SonarQube"
                echo "Checking for code formatting using Prettier"
                echo "Verifying adherence to best practices"
                echo "Running npm run lint for additional checks"
                echo "Code quality check completed"
            }
        }

        stage('Security Scan') {
            steps {
                echo "Performing security scan on the code using OWASP Dependency-Check"
                echo "Identifying vulnerabilities in dependencies"
                echo "Performing static application security testing (SAST) using Snyk"
                echo "Running npm audit to check for security vulnerabilities"
                echo "Security scan completed"
            }
            post {
                always {
                    mail(to: "baren.zemo02@gmail.com",
                         subject: "Security Scan Completed",
                         body: "The Security Scan stage has completed. Check logs for details.")
                }
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying the application to ${TESTING_ENVIRONMENT}"
                echo "Uploading build artifacts to Netlify using Netlify CLI"
                echo "Running post-deployment checks"
                echo "Running npm start to verify deployment success"
                echo "Deployment to testing environment completed."
            }
        }

        stage('Approval') {
            steps {
                echo "Waiting for manual approval from the administrator..."
                sleep(time: 10, unit: 'SECONDS')
                echo "Approval granted. Proceeding to production deployment."
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Deploying the application to ${PRODUCTION_ENVIRONMENT}"
                echo "Uploading final build to production server using SSH/SCP"
                echo "Running post-deployment verification"
                echo "Running npm start to confirm application stability"
                echo "Application successfully deployed to production."
            }
        }
    }
}
