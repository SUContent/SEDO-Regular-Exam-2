pipeline {
    agent any

    
      environment {
            DOTNET_VERSION = "8.0.x"
        }
        
        stages {
            stage('Checkout') {
                steps {
                    checkout scm
                }
            }
        
        stage('Restore dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }
        
        stage('Build') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        
        stage('Run tests') {
            steps {
                bat 'dotnet test  --no-build --verbosity normal'
            }
        }
    }
}
