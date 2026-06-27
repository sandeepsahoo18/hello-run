pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t hello-run .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker rm -f hello-run || true'
                sh 'docker run -d --name hello-run -p 80:80 hello-run'
            }
        }
    }
}
