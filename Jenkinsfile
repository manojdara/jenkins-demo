
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Source code checked out successfully'
            }
        }

        stage('Check Python') {
            steps {
                bat 'python --version'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'python -m unittest -v'
            }
        }
    }

    post {
        success {
            echo 'SUCCESS: All tests passed!'
        }
        failure {
            echo 'FAILURE: Check the console output.'
        }
    }
}
