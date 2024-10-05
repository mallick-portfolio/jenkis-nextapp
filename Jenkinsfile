pipeline {
    agent any
    
    environment {
        NODE_VERSION = '20' // Set Node.js version based on your project
        GIT_URL = 'https://github.com/your-username/your-nextjs-repo.git'
    }

    stages {
        stage('Clone Repository') {
            steps {
                // Replace with your public repository URL
                echo "hello clone"
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    // Ensure Node.js version is correct (if using nvm)
                    echo "hello clone2"
                }
                // Install project dependencies
                echo "hello clone3"
            }
        }

        stage('Build') {
            steps {
                // Run the Next.js build command
                echo "hello clone4"
            }
        }

        stage('Test') {
            steps {
                // Run tests (optional, if you have tests in your project)
                echo "hello clone5"
            }
        }

        stage('Deploy') {
            steps {
                // Add your deployment steps here (if deploying somewhere)
                echo 'Deploying application...'
                // Example: sh 'npm run deploy' or other deployment commands
            }
        }
    }
    
    post {
        always {
            // Clean up workspace after build
            cleanWs()
        }
        success {
            echo 'Build completed successfully!'
        }
        failure {
            echo 'Build failed. Please check the logs!'
        }
    }
}
