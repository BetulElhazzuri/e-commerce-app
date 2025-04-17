pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'python3 -m venv venv'
                sh '. venv/bin/activate && pip install -r requirements.txt'
            }
        }
        stage('Test') {
            steps {
                sh '. venv/bin/activate && pytest tests/'
            }
        }
        stage('UI Test') {
            steps {
                sh '. venv/bin/activate && python tests/test_ui.py'
            }
        }
    }
}