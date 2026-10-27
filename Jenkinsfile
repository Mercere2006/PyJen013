pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies...'
                sh 'python3 -m pip install --upgrade pip'
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Lint') {
            steps {
                echo 'Checking code style with flake8...'
                sh 'flake8 . --count --select=E9,F63,F7,F82 --show-source --statistics'
            }
        }

        stage('Test') {
            steps {
                echo 'Running pytest...'
                sh 'pytest test_app.py'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Executing application...'
                sh 'python3 main.py'
            }
        }
    }
}