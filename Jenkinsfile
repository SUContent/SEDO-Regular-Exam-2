pipeline {
    agent {
        docker {
            image 'mcr.microsoft.com/dotnet/sdk:8.0' // Use a .NET SDK image
        }
    }
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
