pipeline {
    agent any

    environment {
        VERCEL_TOKEN = credentials('vercel-token') // Stored in Jenkins Credentials
    }

    stages {
        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Skipping tests for now...' // Placeholder for future test integration
            }
        }

        stage('Build Project') {
            steps {
                bat 'npm run build'
            }
        }

        stage('Deploy to Vercel') {
            steps {
                bat "npx vercel --prod --yes --token=%VERCEL_TOKEN%"
            }
        }
    }
}