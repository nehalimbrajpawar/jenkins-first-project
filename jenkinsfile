pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t mywebsite .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker rm -f mywebsite-container || true'
                sh 'docker run -d -p 80:80 --name mywebsite-container mywebsite'
            }
        }
    }
}
