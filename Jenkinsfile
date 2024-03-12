pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Checkout the repository
                    checkout scm

                    // Compile the .cpp file
                    sh 'g++ -o app hello.cpp'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Run the compiled .cpp file
                    sh './app'
                }
            }
        }

        stage('Deploy') {
            steps {
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
