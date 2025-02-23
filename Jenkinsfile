pipeline {
    agent any
    stages {
        stage('Checkout the repo') {
            steps {
                sh 'git clone git@github.com:krasezzza/horizons-exam.git'
            }
        }
        stage('Setup .NET environment') {
            steps {
                sh 'apt-get update && apt-get install -y dotnet-sdk-8.0 && dotnet --version'
            }
        }
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
