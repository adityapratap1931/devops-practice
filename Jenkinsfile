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
                sh 'exit 1'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying application..."
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
