pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Checkout the repository
                    checkout scm

                    // Build the Docker image
                    docker.build("cpp-builder")

                    // Compile the .cpp file using the Docker container
                    docker.image("cpp-builder").inside {
                        sh 'g++ -o app hello.cpp'
                    }
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Run the compiled .cpp file using the Docker container
                    docker.image("cpp-builder").inside {
                        sh './app'
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Add deployment steps here (example: copy binary to a server)
                    // Modify the following lines based on your deployment scenario

                    // Copy the compiled binary to the deployment server
                    sh 'scp app user@deployment-server:/path/to/deployment/directory/'

                    // Additional deployment steps can be added based on your needs
                }
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
