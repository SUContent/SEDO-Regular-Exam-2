pipeline {
    agent any
    stages {
        stage('Build and Restore dependencies') {
            steps {
                sh 'dotnet restore && dotnet build --no-restore'
            }
        }
        stage('Run All Tests') {
            steps {
                sh 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
