pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Creating build file...'

                sh '''
                    echo "Hello from Build stage" > app.txt
                '''

                stash name: 'my-app', includes: 'app.txt'
            }
        }

        stage('Test') {
            steps {
                unstash 'my-app'

                sh '''
                    echo "Testing app..."
                    cat app.txt
                '''
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
