pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo "Building application..."

                sh '''
                    echo "Build completed" > build.txt
                    echo "Build Number: $BUILD_NUMBER" >> build.txt
                    echo "Environment: $ENVIRONMENT" >> build.txt
                '''
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

        always {
            archiveArtifacts artifacts: 'build.txt', fingerprint: true
        }
    }
}
