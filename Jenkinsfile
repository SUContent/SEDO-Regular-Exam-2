pipeline {
    agent any

    stages {
         stage('Restore dependencies ') {
            steps {
                bat 'dotnet restore'
            }
        }
       
        stage('Building ') {
            steps {
                bat 'dotnet build'
            }
        }
        stage('Testing ') {
            steps {
                bat 'dotnet test'
            }
        }
        
    }
}
