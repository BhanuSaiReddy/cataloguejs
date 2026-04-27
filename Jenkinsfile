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

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Unit Test') {
            steps {
                sh 'npm test'
            }
        }

    }
}