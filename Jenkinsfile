pipeline {
    agent any
    
    stages {

        stage('Restore  dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build application') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }

        stage('Run all Tests') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
