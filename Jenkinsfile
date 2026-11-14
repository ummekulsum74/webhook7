
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Checking Python application'

                bat '"C:\\Users\\student\\AppData\\Local\\Programs\\Python\\Python312\\python.exe" --version'

                bat '"C:\\Users\\student\\AppData\\Local\\Programs\\Python\\Python312\\python.exe" -m py_compile app.py'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing Python application'

                bat '"C:\\Users\\student\\AppData\\Local\\Programs\\Python\\Python312\\python.exe" -c "import app; print(\'Application imported successfully\')"'
            }
        }

        stage('Run Application') {
            steps {
                echo 'Running Python application'

                bat '"C:\\Users\\student\\AppData\\Local\\Programs\\Python\\Python312\\python.exe" app.py'
            }
        }
    }

    post {
        success {
            echo 'CI Pipeline completed successfully'
        }

        failure {
            echo 'CI Pipeline failed'
        }
    }
}
