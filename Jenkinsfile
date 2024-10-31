pipeline {
    agent any

    environment {
        NODE_VERSION = '14' // or your Node.js version
    }

    stages {
        stage('Clone Repository') {
            steps {
                echo 'Cloning repository...'
                checkout scm
            }
        }
        
        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies...'
                script {
                    if (isUnix()) {
                        bat "nvm install ${NODE_VERSION}"
                        bat "nvm use ${NODE_VERSION}"
                        bat 'npm install'
                    } else {
                        bat "nvm install ${NODE_VERSION}"
                        bat "nvm use ${NODE_VERSION}"
                        bat 'npm install'
                    }
                }
            }
        }

        stage('Build Application') {
            steps {
                echo 'Building application...'
                script {
                    if (isUnix()) {
                        bat 'npm run build'
                    } else {
                        bat 'npm run build'
                    }
                }
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                // Add your Windows-compatible deployment commands here
            }
        }
    }

    post {
        success {
            echo 'Deployment succeeded.'
        }
        failure {
            echo 'Deployment failed.'
        }
    }
}
