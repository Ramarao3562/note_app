pipeline {
    agent any

    environment {
        PYTHON_ENV = "python3"
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Ramarao3562/note_app.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies...'
                bat '${PYTHON_ENV} -m pip install -r requirements.txt'
            }
        }

        stage('Build Application') {
            steps {
                echo 'Building application...'
                // Add any other build commands here
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                bat '${PYTHON_ENV} app.py'
            }
        }
    }

    post {
        always {
            cleanWs()
        }
        success {
            echo 'Deployment successful!'
        }
        failure {
            echo 'Deployment failed.'
        }
    }
}
