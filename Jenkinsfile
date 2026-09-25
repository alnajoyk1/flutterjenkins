pipeline {
    agent any

    stages {

        stage('Check Flutter') {
            steps {
                sh 'flutter --version'
            }
        }

        stage('Get Dependencies') {
            steps {
                sh 'flutter pub get'
            }
        }

        stage('Build APK') {
            steps {
                sh 'flutter build apk --release'
            }
        }
    }

    post {
        success {
            echo 'Flutter APK build completed successfully!'
        }

        failure {
            echo 'Flutter build failed. Check the console output.'
        }
    }
}