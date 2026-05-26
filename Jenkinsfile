pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t mywebsite .'
            }
        }

        stage('Remove Old Container') {
            steps {
                bat 'docker rm -f mywebsite || exit 0'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker run -d --name mywebsite -p 8081:80 mywebsite'
            }
        }
    }
}
