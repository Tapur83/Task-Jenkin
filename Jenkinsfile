pipeline {
    agent any

    environment {
        DIRECTORY_PATH = "/Professioal Development/jenkins" 
        TESTING_ENVIRONMENT = "Netlify"       
        PRODUCTION_ENVIRONMENT = "Tapur Aggarwal" 
    }

    stages {
        
        stage('Build') {
            steps {
                echo "Fetching the source code from ${DIRECTORY_PATH}"
                echo "Compiling the code and generating artifacts"
                echo "Build stage completed successfully!"
            }
        }

       
        stage('Test') {
            steps {
                echo "Running unit tests"
                echo "Running integration tests"
            }
            post {
                success {
                    mail(to: "tapur4828.be23@chitkara.edu.in",
                         subject: "Test Stage Completed",
                         body: "The Test stage has completed successfully. Check logs for details.")
                }
                failure {
                    mail(to: "tapur4828.be23@chitkara.edu.in",
                         subject: "Test Stage Failed",
                         body: "The Test stage has failed. Check logs for details.")
                }
            }
        }

      
        stage('Code Quality Check') {
            steps {
                echo "Performing code quality check"
                echo "Code quality check completed successfully!"
            }
        }

           stage('Security Scan') {
            steps {
                echo "Performing security scan on the code"
                echo "Identifying vulnerabilities (simulated)"
                echo "Security scan completed successfully!"
            }
            post {
                always {
                    mail(to: "tapur4828.be23@chitkara.edu.in",
                         subject: "Security Scan Completed",
                         body: "The Security Scan stage has completed. Check logs for details.")
                }
            }
        }

       
        stage('Deploy to Testing') {
            steps {
                echo "Deploying the application to ${TESTING_ENVIRONMENT}"
                echo "Deployment to testing environment completed successfully!"
            }
        }

       
        stage('Approval') {
            steps {
                echo "Waiting for approval..."
                sleep(time: 10, unit: 'SECONDS')
                echo "Approval received!"
            }
        }

       
        stage('Deploy to Production') {
            steps {
                echo "Deploying the application to ${PRODUCTION_ENVIRONMENT}"
                echo "Deployment to production environment completed successfully!"
            }
        }
    }

    post {
        success {
            echo "Pipeline completed successfully!"
            mail(to: "tapur4828.be23@chitkara.edu.in",
                 subject: "Pipeline Success",
                 body: "The pipeline has completed successfully. Check logs for details.")
        }
        failure {
            echo "Pipeline failed. Check the logs for details."
            mail(to: "tapur4828.be23@chitkara.edu.in",
                 subject: "Pipeline Failure",
                 body: "The pipeline has failed. Check logs for details.")
        }
    }
}
    }
}
