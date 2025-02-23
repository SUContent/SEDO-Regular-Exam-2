pipeline {
    agent any

    stages {
        stage('Restore dependencies') {
            steps {
                bat 'dotnet restore'  
            }
        }
        
        stage('Run Build') {
            steps {
                bat 'dotnet build --no-restore'  
            }
        }
        
        stage('Run All Test') {
            steps {
                bat 'dotnet test --no-build --verbosity normal' 
            }
        }
    }
}
