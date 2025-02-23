pipeline {
    agent any

    environment {
        DOTNET_VERSION = "8.0.x"
    }

    stages {
        stage('Restore dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build Application') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }

        stage('Run All Tests') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
