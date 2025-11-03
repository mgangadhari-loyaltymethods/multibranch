pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Automatically checks out the current branch hi bye
                git branch: "${env.BRANCH_NAME}", url: 'https://github.com/mgangadhari-loyaltymethods/multibranch.git'
            }
        }

        stage('Build') {
            steps {
                echo "Building the project on branch: ${env.BRANCH_NAME}"
                // Example: compile or install dependencies
                sh 'echo "Build step completed"'
            }
        }

        stage('Test') {
            steps {
                echo "Running tests on branch: ${env.BRANCH_NAME}"
                // Example: run unit tests
                sh 'echo "Tests completed successfully"'
            }
        }

        stage('Deploy') {
            when {
                branch 'main' // only deploy from main branch
            }
            steps {
                echo "Deploying application from ${env.BRANCH_NAME}"
                sh 'echo "Deployment completed"'
            }
        }
    }

    post {
        success {
            echo "Build succeeded for branch: ${env.BRANCH_NAME}"
        }
        failure {
            echo "Build failed for branch: ${env.BRANCH_NAME}"
        }
    }
}

