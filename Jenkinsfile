pipeline {
    agent any

    environment {
        APP_NAME = 'devops-app'
        ENVIRONMENT = 'production'
    }

    stages {
        stage('Build') {
            steps {
                echo "Building ${env.APP_NAME}"
                echo "Environment: ${env.ENVIRONMENT}"
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying ${env.APP_NAME} to ${env.ENVIRONMENT}"
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed!'
        }
    }
}
