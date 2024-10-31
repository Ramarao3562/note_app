pipeline {
    agent any

    environment {
        PYTHON_ENV = "python"
    }

    stages {
        stage('Checkout') {
            steps {
               git branch: 'main', url: 'https://github.com/Ramarao3562/note_app.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies...'
                bat 'C:\\Users\\achut\\AppData\\Local\\Programs\\Python\\Python313\\python.exe -m pip install -r requirements.txt'
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
                bat 'C:\\Users\\achut\\AppData\\Local\\Programs\\Python\\Python313\\python.exe app.py'
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
