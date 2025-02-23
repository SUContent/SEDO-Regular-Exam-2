pipeline {
    agent any

    stages {

        stage('Restore dependencies') {
            steps {
                powershell 'dotnet restore'
            }
        }

        stage('Build application') {
            steps {
                powershell 'dotnet build --no-restore'
            }
        }

        stage('Run all Tests') {
            steps {
                powershell 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
