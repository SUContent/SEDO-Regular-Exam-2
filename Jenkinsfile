pipeline {
    agent any

    environment {
        DOTNET_VERSION = '8.0.x' 
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Setup .NET') {
            steps {
                bat '''
                dotnet --version || (
                powershell -Command "Set-ExecutionPolicy Unrestricted -Scope Process -Force; `
                Invoke-WebRequest -Uri https://dot.net/v1/dotnet-install.ps1 -OutFile dotnet-install.ps1; `
                & .\\dotnet-install.ps1 --version %DOTNET_VERSION%"
                )
                set PATH=%USERPROFILE%\\.dotnet;%PATH%
                '''
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
        
        stage('Test') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
