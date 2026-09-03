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
            steps {
                echo "Deploying to ${params.ENVIRONMENT}..."
            }
        }
    }

    post {
        success {
            echo "BUILD SUCCESSFUL!"
        }

        failure {
            echo "BUILD FAILED!"
        }

        always {
            echo "Jenkins pipeline finished."
        }
    }
}
