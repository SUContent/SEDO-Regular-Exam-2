pipeline {
    agent any

    environment {
        DOTNET_ROOT = "/root/.dotnet"
        PATH = "/root/.dotnet:$PATH"
    }

    stages {
        stage('Restore Dependencies') {
            steps {
                script {
                    sh '/root/.dotnet/dotnet restore'
                }
            }
        }

        stage('Build the application') {
            steps {
                script {
                    sh '/root/.dotnet/dotnet build'
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    sh '/root/.dotnet/dotnet test'
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
