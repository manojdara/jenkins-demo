
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Source code is available in the workspace'
                checkout scm
            }
        }

        stage('Check Python') {
            steps {
                sh 'python3 --version'
            }
        }

        stage('Test') {
            steps {
                sh 'python3 -m unittest -v'
            }
        }

        stage('Package') {
            steps {
                sh 'zip -j calculator-demo.zip calculator.py test_calculator.py'
                archiveArtifacts artifacts: 'calculator-demo.zip',
                                 fingerprint: true
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check the console output.'
        }
    }
}
