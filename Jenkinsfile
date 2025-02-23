pipeline {
    agent any
    
    environment {
        DOTNET_VERSION = '8.0.x'
    }

    stages {
        stage('Restore Dependencies') {
            steps {
                script {
                    bat 'dotnet restore'
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    bat 'dotnet build --no-restore'
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    bat 'dotnet test --no-build --verbosity normal'
                }
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}
