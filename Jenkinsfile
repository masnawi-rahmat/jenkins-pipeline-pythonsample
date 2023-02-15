pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t my-python-app .'
            }
        }
        stage('Test') {
            steps {
                sh 'docker run my-python-app python -m unittest discover'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker run -p 5000:5000 my-python-app'
            }
        }
    }
}
