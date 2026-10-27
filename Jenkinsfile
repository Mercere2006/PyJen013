pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies...'
                bat '"C:/Users/srypo/AppData/Local/Python/bin/python.exe" -m pip install --upgrade pip'
                bat '"C:/Users/srypo/AppData/Local/Python/bin/python.exe" -m pip install -r requirements.txt'
            }
        }

        stage('Lint') {
            steps {
                echo 'Checking code style with flake8...'
                bat '"C:/Users/srypo/AppData/Local/Python/bin/python.exe" -m flake8 . --count --select=E9,F63,F7,F82 --show-source --statistics'
            }
        }

        stage('Test') {
            steps {
                echo 'Running pytest...'
                bat '"C:/Users/srypo/AppData/Local/Python/bin/python.exe" -m pytest test_app.py'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Executing application...'
                bat '"C:/Users/srypo/AppData/Local/Python/bin/python.exe" main.py'
            }
        }
    }
}