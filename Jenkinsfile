pipeline {
    agent any

    environment {
        FLUTTER_HOME = '/home/alnajoyk1/flutter'
        PATH = "${FLUTTER_HOME}/bin:${PATH}"
    }

    stages {

        stage('Check Flutter') {
            steps {
                sh 'which flutter'
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