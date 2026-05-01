pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/your-username/python-jenkins-demo.git'
            }
        }

        stage('Test') {
            steps {
                sh 'pip install pytest'
                sh 'pytest'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t python-demo .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d --name python-demo-container python-demo || true'
            }
        }
    }
}