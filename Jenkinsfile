pipeline {
    agent any
    stages {
        stage('Restore dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Build project') {
            steps {
                bat 'dotnet build --configuration Release --no-restore'
            }
        }
        stage('Run tests') {
            steps {
                bat 'dotnet test --configuration Release --no-build --verbosity normal'
            }
        }
    }
}
