pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo "Building application..."
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
            }
        }

        stage('Deploy') {
            when {
                expression {
                    params.ENVIRONMENT == 'prod'
                }
            }
            steps {
                echo "Deploying to PRODUCTION..."
            }
        }
    }

    post {
        success {
            echo "Pipeline completed successfully!"
        }

        failure {
            echo "Pipeline failed!"
        }
    }
}
