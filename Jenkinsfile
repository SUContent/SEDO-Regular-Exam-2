pipeline {
    agent any
    stages {
        stage('Build and Restore dependencies') {
            steps {
                sh 'dotnet restore && dotnet build --no-restore'
            }
        }
        stage('Run Tests') {
            steps {
                sh 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
