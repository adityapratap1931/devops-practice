stage('Build') {
    steps {
        echo "Building application..."

        sh '''
            echo "Hello from Jenkins Workspace" > workspace.txt
            echo "Build Number: $BUILD_NUMBER" >> workspace.txt
        '''
    }
}
