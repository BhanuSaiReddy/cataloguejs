pipeline {
    agent any

    stages {

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
                sh 'npm install'
                sh 'npm run build'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying application version..."
            }
        }
    }
}