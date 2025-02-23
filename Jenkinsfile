pipeline {
    agent any

    stages {
        stage('Checkout Repository') {
            steps {
                checkout scm
            }
        }

        stage('Setup .NET') {
            steps {
                script {
                    bat "wget https://dot.net/v1/dotnet-install.sh -O dotnet-install.sh"
                    bat "chmod +x dotnet-install.sh"
                    bat "./dotnet-install.sh --version $DOTNET_VERSION"
                    bat "export PATH=$HOME/.dotnet:$PATH"
                }
            }
        }

        stage('Restore Dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build Project') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
