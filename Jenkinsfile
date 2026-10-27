pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies...'
                bat 'python -m pip install --upgrade pip'
                bat 'pip install -r requirements.txt'
            }
        }

        stage('Lint') {
            steps {
                echo 'Checking code style with flake8...'
                bat 'flake8 . --count --select=E9,F63,F7,F82 --show-source --statistics'
            }
        }

        stage('Test') {
            steps {
                echo 'Running pytest...'
                bat 'pytest test_app.py'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Executing application...'
                bat 'python main.py'
            }
        }
    }
}