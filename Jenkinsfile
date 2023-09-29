pipeline {
    agent { 
        node {
            label 'docker-agent-alpine'
        }
    }

    tools {
        go 'golang_instalacion'
    }

    environment {
        GO114MODULE = 'on'
        CGO_ENABLED = 0 
        GOPATH = "${JENKINS_HOME}/jobs/${JOB_NAME}/builds/${BUILD_ID}"
    }

    triggers {
        pollSCM '*/5 * * * *'
    }

    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                echo "Compilando la app con "
                go version
                go build -o main
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                echo "Testiando si todo va chido xD"
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "Desplegando la app"
                ./main
                '''
            }
        }
    }
}