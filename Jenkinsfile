
pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
                checkout scm
            }
        }

        stage('Test') {
            steps {
                bat '''
                echo Checking Python installation...

                "C:\\Users\\Dell\\AppData\\Local\\Programs\\Python\\Python314\\python.exe" --version

                echo Running unit tests...

                "C:\\Users\\Dell\\AppData\\Local\\Programs\\Python\\Python314\\python.exe" -m unittest
                '''
            }
        }

        stage('Run Application') {
            steps {
                bat '''
                echo Running Python application...

                "C:\\Users\\Dell\\AppData\\Local\\Programs\\Python\\Python314\\python.exe" app.py
                '''
            }
        }
    }

    post {
        success {
            echo 'Python Pipeline Executed Successfully!'
        }

        failure {
            echo 'Python Pipeline Failed!'
        }
    }
}
