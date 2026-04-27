pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                // Pull code from Git (change URL if needed)
                git url: 'https://github.com/BhanuSaiReddy/cataloguejs.git', branch: 'main'
            }
        }

        stage('Read Version') {
            steps {
                script {
                    def packageJSON = readJSON file: 'package.json'
                    def appVersion = packageJSON.version
                    echo "App version: ${appVersion}"
                }
            }
        }

        stage('Build') {
            steps {
                echo "Building application..."
                // Example: sh 'npm install && npm run build'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying application version..."
            }
        }
    }
}