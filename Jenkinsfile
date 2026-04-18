pipeline {
    agent any
    environment {
        APP_NAME = 'my-app'
        VERSION  = '1.0.0'
    }
    stages {
        stage('Write Files') {
            steps {
                sh 'echo "App: $APP_NAME" > info.txt'
                sh 'echo "Version: $VERSION" >> info.txt'
                sh 'echo "Build: $BUILD_NUMBER" >> info.txt'
                sh 'echo "Workspace: $WORKSPACE" >> info.txt'
            }
        }
        stage('Read Files') {
            steps {
                echo 'Contents of info.txt:'
                sh 'cat info.txt'
            }
        }
        stage('Explore Workspace') {
            steps {
                echo 'Everything in the workspace:'
                sh 'ls -la $WORKSPACE'
                echo "Full path of our file:"
                sh 'realpath info.txt'
            }
        }
    }
    post {
        always {
            archiveArtifacts artifacts: 'info.txt'
        }
    }
}
