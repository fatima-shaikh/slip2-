pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Build stage – nothing to compile for static website'
            }
        }

        stage('Deploy to Localhost') {
            steps {
                echo 'Deploying website to XAMPP htdocs...'
                bat 'xcopy * C:\\xampp\\htdocs /E /Y'
            }
        }
    }
}
