pipeline {
    agent any

    stages {
        stage('w/o docker') {
            steps {
                sh 'echo "Without Docker"'
                sh 'ls -la'
                sh 'touch container-no.txt'
            }
        }
        
        stage('w/ docker') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh 'echo "With Docker"'
                sh 'npm --version'
                sh 'touch container-yes.txt'
                sh 'ls -la'
            }
        }
    }
}
