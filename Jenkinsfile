pipeline {
    agent any

    stages {
        stage('Restore dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build application') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }

        stage('Run unit and integration tests') {
            steps {
                bat 'dotnet test'
            }
        }
    }
}
