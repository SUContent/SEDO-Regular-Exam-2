pipeline {
    agent any
    stages {
        stage('Checkout the repo') {
            steps {
                sh 'rm -rf horizons-exam && git clone https://github.com/krasezzza/horizons-exam.git'
            }
        }
        stage('Setup .NET environment') {
            steps {
                sh 'apt-get install -y dotnet-sdk-8.0 && dotnet --version'
            }
        }
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
