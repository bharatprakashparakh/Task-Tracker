pipeline {
    agent any

    tools {
        nodejs 'NodeJS 21.1'  // Ensure Node.js v14 is used (make sure this version is installed in Jenkins)
    }

    // environment {
    //     NODE_OPTIONS = '--openssl-legacy-provider'  // To avoid OpenSSL-related issues in newer versions of Node.js
    // }

    stages {
        stage('Checkout') {
            steps {
                cleanWs()  // Clean the workspace before checkout
                echo "Checking out the repository..."
                checkout scm  // Checkout the code from the repository
            }
        }
        
        stage('Install Dependencies') {
            steps {
                script {
                    echo "Installing dependencies..."
                    sh 'npm install'  // Install dependencies using npm
                }
            }
        }

        stage('Build') {
            steps {
                echo "Building the React project..."
                sh 'npm run build'  // Run the build script as defined in your package.json
            }
        }

    }

  
}
