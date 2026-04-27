pipeline {
    agent { label 'agent-1' }

    stages {

        stage('Checkout Code') {
            steps {
                git url: 'https://github.com/BhanuSaiReddy/cataloguejs.git', branch: 'main'
            }
        }

        stage('Read Version') {
            steps {
                script {
                    def packageJSON = readFile 'package.json'
                    def json = new groovy.json.JsonSlurper().parseText(packageJSON)

                    echo "App Version: ${json.version}"
                }
            }
        }

        stage('Install Dependencies') {
            steps {
                sh '''
                    node -v
                    npm -v
                    npm install
                '''
            }
        }

        stage('Unit Test') {
            steps {
                sh 'npm test'
            }
        }
    }
}