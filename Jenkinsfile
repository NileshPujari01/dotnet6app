pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from your repository
                git 'https://github.com/NileshPujari01/dotnet6app.git'
            }
        }
        
        stage('Restore') {
            steps {
                // Restore dependencies
                script {
                    bat 'dotnet restore'
                }
            }
        }

        stage('Build') {
            steps {
                // Build the project
                script {
                    bat 'dotnet build --configuration Release'
                }
            }
        }

        stage('Test') {
            steps {
                // Run tests
                script {
                    bat 'dotnet test --configuration Release'
                }
            }
        }

        stage('Publish') {
            steps {
                // Publish the project
                script {
                    bat 'dotnet publish --configuration Release --output ./publish'
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
