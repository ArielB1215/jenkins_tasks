pipeline {
    agent any
    environment {
        APP_NAME = 'my-app'
        VERSION  = '1.0.0'
    }
    stages {
        stage('Global Variables') {
            steps {
                echo "App     : ${env.APP_NAME}"
                echo "Version : ${env.VERSION}"
            }
        }
        stage('Override Version') {
            environment {
                VERSION = '2.0.0-beta'
            }
            steps {
                echo "Version inside this stage : ${env.VERSION}"
            }
        }
        stage('After Override') {
            steps {
                echo "Version back to : ${env.VERSION}"
            }
        }
    }
}
