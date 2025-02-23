pipeline {
    agent any

    environment {
        DOTNET_VERSION = "8.0"
    }

    stages {
        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Setup .NET') {
            steps {
                script {
                    sh 'dotnet --version'
                }
            }
        }

        stage('Restore Dependencies') {
            steps {
                sh 'dotnet restore'
            }
        }

        stage('Build Application') {
            steps {
                sh 'dotnet build --no-restore'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'dotnet test --no-build --verbosity normal'
            }
        }
    }

    post {
        success {
            echo "Build and tests executed successfully!"
        }
        failure {
            echo "Build or tests failed!"
        }
    }
}
