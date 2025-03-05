pipeline {
    agent any

    environment {
        SOURCE_CODE_DIR = 'SEMESTER-4/Professioal Development/jenkins' 
        TEST_ENV = 'stages'         
        PROD_ENV = 'tapur'     
    }

    stages {
        stage('Build') {
            steps {
                echo "Fetch the source code from the directory path specified by the environment variable: ${env.SOURCE_CODE_DIR}"
                echo "Compile the code and generate any necessary artifacts"
            }
        }

        stage('Test') {
            steps {
                echo "Running unit tests"
                echo "Running integration tests"
            }
        }

        stage('Code Quality Check') {
            steps {
                echo "Check the quality of the code"
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploy the application to a testing environment specified by the environment variable: ${env.TEST_ENV}"
            }
        }

        stage('Approval') {
            steps {
                echo "Waiting for manual approval..."
                sleep 10 // Simulate a 10-second pause for manual approval
                echo "Approval received, continuing pipeline."
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Deploy the code to the production environment specified by the environment variable: ${env.PROD_ENV}"
            }
        }
    }
}
