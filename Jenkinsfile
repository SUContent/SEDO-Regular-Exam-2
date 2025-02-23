pipeline {
    agent any
    
    stages {
        stage('Setup .NET') {
            steps {
            bat 'dotnet --version || (powershell -Command "Invoke-WebRequest -Uri https://dot.net/v1/dotnet-install.ps1 -OutFile dotnet-install.ps1; powershell -File dotnet-install.ps1 --version %DOTNET_VERSION%")'
            bat 'set PATH=%USERPROFILE%\\.dotnet;%PATH%'
            bat 'dotnet --version' // Check if .NET is installed
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
