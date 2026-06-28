pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Arpita14-web/jenkins-docker-lab.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t mywebsite .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f mycontainer || true'
                sh 'docker run -d -p 8081:80 --name mycontainer mywebsite'
            }
        }
    }
}