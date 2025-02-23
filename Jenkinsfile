pipeline {
    agent any
    
    stages {          
        stage('Restore Dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }
        
        stage('Build') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        stage('Run Unit Tests') {
            steps {
                bat 'dotnet test "Horizons.Tests.Unit/Horizons.Tests.Unit.csproj" --no-build --verbosity normal'
            }
        }

        stage('Run Integration Tests') {
            steps {
                bat 'dotnet test "Horizons.Tests.Integration/Horizons.Tests.Integration.csproj" --no-build --verbosity normal'
            }
        }
        /*stage('Run all tests') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }*/
    }   
}