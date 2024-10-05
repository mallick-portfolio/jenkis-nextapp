pipeline {
    agent any
    
    environment {
        NODE_VERSION = '22' // Set Node.js version based on your project
        GIT_URL = 'https://github.com/your-username/your-nextjs-repo.git'
    }

    stages {
        stage('Clone Repository') {
            steps {
                // Replace with your public repository URL
                git url: $GIT_URL, branch: 'main'
            }
        }

        // stage('Install Dependencies') {
        //     steps {
        //         script {
        //             // Ensure Node.js version is correct (if using nvm)
        //             sh "nvm install $NODE_VERSION"
        //         }
        //         // Install project dependencies
        //         sh 'npm install'
        //     }
        // }

        // stage('Build') {
        //     steps {
        //         // Run the Next.js build command
        //         sh 'npm run build'
        //     }
        // }

        // stage('Test') {
        //     steps {
        //         // Run tests (optional, if you have tests in your project)
        //         sh 'npm run test'
        //     }
        // }

        // stage('Deploy') {
        //     steps {
        //         // Add your deployment steps here (if deploying somewhere)
        //         echo 'Deploying application...'
        //         // Example: sh 'npm run deploy' or other deployment commands
        //     }
        // }
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
