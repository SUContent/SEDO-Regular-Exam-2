pipeline {
    agent any
  
    stages {
        stage('Restore Dependencies') {
            steps {
                sh 'dotnet restore'
            }
        }
        stage('Build') {
            steps {
                sh 'dotnet build --no-restore'
            }
        }
        stage('Run Tests') {
            steps {
                // Adjust the path if needed. Using forward slashes for Linux.
                sh 'dotnet test --no-build --verbosity normal'
            }
        }
    }
  
}
