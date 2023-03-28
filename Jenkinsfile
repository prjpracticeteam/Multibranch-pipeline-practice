pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'npm install'
                sh 'npm run build'
            }
        }
        stage('Test') {
            steps {
                sh 'npm run test'
            }
        }
        stage('Deploy to Dev') {
            when {
                branch 'dev'
            }
            environment {
                SERVER = 'dev.example.com'
            }
            steps {
                sh 'npm run deploy --server=$SERVER'
            }
        }
        stage('Deploy to Prod') {
            when {
                branch 'master'
            }
            environment {
                SERVER = 'prod.example.com'
            }
            steps {
                sh 'npm run deploy --server=$SERVER'
            }
        }
    }
}
