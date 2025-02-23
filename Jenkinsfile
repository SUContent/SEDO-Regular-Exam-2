pipeline {
    agent any

    environment {
        DOTNET_ROOT = '/root/.dotnet'
        PATH = "${DOTNET_ROOT}:${env.PATH}"
    }

    stages {
        stage('Verify .NET Version') {
            steps {
                sh '/root/.dotnet/dotnet --version'
            }
        }

        stage('Restore') {
            steps {
                sh '/root/.dotnet/dotnet restore'
            }
        }

        stage('Build') {
            steps {
                sh '/root/.dotnet/dotnet build --no-restore'
            }
        }

        stage('Test') {
            steps {
                sh '/root/.dotnet/dotnet test --no-build --verbosity-normal'
            }
        }
    }
}
