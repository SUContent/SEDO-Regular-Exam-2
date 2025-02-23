pipeline {
    agent any

    environment {
        DOTNET_VERSION = '8.0.x'
    }

    stages {

        stage('Setup .NET') {
    steps {
        script {
            // Download .NET SDK version 8.0.0
            bat "curl -sSL https://dotnetcli.azureedge.net/dotnet/Sdk/8.0.0/dotnet-sdk-8.0.0-linux-x64.tar.gz -o dotnet-sdk-8.0.0-linux-x64.tar.gz"
            
            // Check if the downloaded file is a tarball (optional but useful for debugging)
            sh "file dotnet-sdk-8.0.0-linux-x64.tar.gz"

            // Extract the SDK to a local directory
            sh "mkdir -p $HOME/dotnet"
            sh "tar -xzf dotnet-sdk-8.0.0-linux-x64.tar.gz -C $HOME/dotnet"
            
            // Add the dotnet SDK to the PATH
            sh "export PATH=$HOME/dotnet:$PATH"
        }
    }
}
        
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

        stage('Run Integration Tests') {
            steps {
                sh 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
