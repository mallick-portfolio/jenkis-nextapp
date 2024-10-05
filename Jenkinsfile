pipeline {
    agent any

    tools {
        nodejs 'mynode' // The name you gave in Global Tool Configuration
    }

    stages {
        stage('Checkout') {
            steps {
                // Clone the repository from GitHub
                git branch: 'main', url: 'https://github.com/mallick-portfolio/jenkis-nextapp.git'
            }
        }
        
        stage('Install Dependencies') {
            steps {
                // Install Node.js dependencies
                sh 'npm install'
            }
        }
        
        stage('Build') {
            steps {
                // Build the Next.js app
                sh 'npm run build'
            }
        }
        
        stage('Deploy') {
            steps {
                // You can define the steps to deploy your app.
                // This depends on your deployment strategy, e.g., SSH to a server, push to a container registry, etc.
                echo 'Deploying the application...'
                // Example: Deploy to a server via SCP (you need to set up SSH credentials)
                // sh 'scp -r ./* user@yourserver:/path/to/deployment'
            }
        }
    }
    
    post {
        always {
            echo 'Cleaning up workspace...'
            cleanWs() // Clean up the workspace after each build
        }
        
        success {
            echo 'Pipeline succeeded!'
        }
        
        failure {
            echo 'Pipeline failed!'
        }
    }
}
