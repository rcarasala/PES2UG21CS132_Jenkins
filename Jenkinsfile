pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                // You can print more random stuff or perform tasks here
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
                // You can print more random stuff or perform tasks here
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // You can print more random stuff or perform tasks here
            }
        }
    }

    post {
        success {
            echo 'All stages passed successfully!'
        }
        failure {
            echo 'Pipeline failed'
        }
    }
}
