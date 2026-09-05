pipeline {
    agent any

    environment {
        APP_NAME = 'devops-app'
        ENVIRONMENT = 'production'
    }

    stages {

        stage('Checkout') {
            steps {
                echo 'Code checked out from GitHub'
            }
        }

        stage('Build') {
            steps {
                echo "Building ${env.APP_NAME}..."
            }
        }

        stage('Test') {
            parallel {
                stage('Unit Test') {
                    steps {
                        echo 'Running Unit Tests...'
                    }
                }

                stage('Security Test') {
                    steps {
                        echo 'Running Security Tests...'
                    }
                }
            }
        }

        stage('Approval') {
            steps {
                input message: 'Approve production deployment?', ok: 'Deploy'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying ${env.APP_NAME} to ${env.ENVIRONMENT}..."
            }
        }
    }

    post {
        success {
            echo 'CI/CD Pipeline completed successfully!'
        }

        failure {
            echo 'CI/CD Pipeline failed!'
        }
    }
}
