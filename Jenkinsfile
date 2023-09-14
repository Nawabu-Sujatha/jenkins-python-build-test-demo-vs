pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: 'main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/vastevenson/pytest-intro-vs.git']]])
            }
        }
        stage('Build') {
            steps {
                git branch: 'main', url: 'https://github.com/Nawabu-Sujatha/jenkins-python-build-test-demo-vs.git'
                sh 'python3 ops.py'
            }
        }
        stage('Test') {
            steps {
                sh 'python3 -m pytest'
            }
        }
    }
}
