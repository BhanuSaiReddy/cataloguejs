pipeline {
    agent any

    stages {

        stage('Debug PATH') {
            steps {
                sh '''
                    whoami
                    echo $PATH
                    which node
                    which npm
                    node -v
                    npm -v
                '''
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