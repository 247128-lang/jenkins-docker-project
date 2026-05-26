pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git 'https://github.com/247128-lang/jenkins-docker-project.git'
            }
        }

        stage('Remove Old Container') {
            steps {
                bat 'docker rm -f mywebsite || exit 0'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t mywebsite .'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker run -d --name mywebsite -p 8081:80 mywebsite'
            }
        }
    }
}
