kpipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building application...'
                sh '''
                    echo "Hello from Jenkins Workspace" > workspace.txt
                    echo "Build Number: $BUILD_NUMBER" >> workspace.txt
                '''
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
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

