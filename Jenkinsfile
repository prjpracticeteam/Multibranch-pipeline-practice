pipeline {
    agent any

    stages {         
        stage('Deploy to Dev') {
            when {
                branch 'dev'
            }
            environment {
                SERVER = 'dev.example.com'
            }
            steps {
                echo 'Dev Branch'
            }
        }
        stage('Deploy to Prod') {
            when {
                branch 'main'
            }
            environment {
                SERVER = 'prod.example.com'
            }
            steps {
                echo 'Main branch'
            }
        }
    }
}
