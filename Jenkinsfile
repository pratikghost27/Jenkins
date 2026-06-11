pipeline {
    agent any                    // run on any available agent

    environment {                // define env variables
        APP_NAME = "my-app"
    }

    stages {
        stage('Checkout') {      // stage 1
            steps {
                echo "Cloning repo..."
                checkout scm     // pulls the connected repo
            }
        }

        stage('Build') {         // stage 2
            steps {
                echo "Building ${env.APP_NAME}..."
                sh 'ls -la'
            }
        }

        stage('Test') {          // stage 3
            steps {
                echo "Running tests..."
                sh 'echo "All tests passed!"'
            }
        }
    }

    post {                       // runs after all stages
        success {
            echo "Pipeline succeeded!"
        }
        failure {
            echo "Pipeline failed!"
        }
        always {
            echo "Build #${env.BUILD_NUMBER} finished."
        }
    }
}
