pipeline {
    agent any
    tools {
        go 'go1'
    }
    environment {
        CGO_ENABLED = 0 
        GOPATH = "${JENKINS_HOME}/jobs/${JOB_NAME}/builds/${BUILD_ID}"
    }
    stages {        
        stage('Pre Test') {
            steps {
                echo 'Installing dependencies'
                bat 'go version'
            }
        }
        
        stage('Build') {
            steps {
                echo 'Compiling and building'
                bat 'go build'
            }
        }

        stage('Test') {
            steps {
                echo 'Running test'
                bat 'go test -v'
            }
        }
    } 
}
