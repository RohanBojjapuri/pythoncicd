
pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch:'main',
                    url:'https://github.com/RohanBojjapuri/pythoncicd.git'
            }
        }

        stage('Test') {
            steps {
                bat 'python --version'
                bat 'python -m unittest'
            }
        }

        stage('Run Application') {
            steps {
                bat 'python app.py'
            }
        }
    }

    post {
        success {
            echo 'Python Pipeline Successful!'
        }

        failure {
            echo 'Python Pipeline Failed!'
        }
    }
}
