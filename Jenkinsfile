pipeline {
    agent { 
        node {
            label 'docker-agent-alpine'
            }
      }
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                java --version
                javac --version
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                echo "in the middle of running tests"
                javac Main.java
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "doing delivery stuff.."
                java Main
                '''
            }
        }
    }
}