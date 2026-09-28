pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                bat 'python --version'
                bat 'python -m venv .venv'
                bat '.venv\\Scripts\\python.exe -m pip install --upgrade pip'
                bat '.venv\\Scripts\\python.exe -m pip install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                bat '.venv\\Scripts\\python.exe -m pytest -v'
            }
        }

        stage('Build') {
            steps {
                bat '.venv\\Scripts\\python.exe -m py_compile app.py test_app.py'
            }
        }
    }

    post {
        success {
            echo 'Build and tests completed successfully!'
        }

        failure {
            echo 'Pipeline failed. Check the console output.'
        }
    }
}