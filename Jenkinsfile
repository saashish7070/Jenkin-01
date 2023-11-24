pipeline {
    agent {
        docker {
            // Use an official Python runtime as a base image
            image 'python:3.8'
        }
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout your code from the version control system
                checkout scm
            }
        }

        stage('Build and Run') {
            steps {
                // Install any dependencies required by your Python code
                // sh 'pip install -r requirements.txt'

                // Run your Python script
                sh 'python python.py'
            }
        }
    }

    post {
        always {
            // Clean up any resources if necessary
            sh 'docker stop $(docker ps -aq)'
            sh 'docker rm $(docker ps -aq)'
        }
    }
}
