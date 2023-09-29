pipeline {
    agent {
        docker {
            image 'jenkins:2.325.2-jdk11'
        }
    }

    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                echo "Compilando la app"
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
                '''
            }
        }
    }
}