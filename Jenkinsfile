/*

ASSUMPTIONS:
  Machine runs on Windows
  dotnet is installed and is in PATH
  
*/
pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                bat 'dotnet build'
            }
        }
        stage('run Tests') {
            steps {
                bat 'dotnet test'
            }
        }
    }
}
