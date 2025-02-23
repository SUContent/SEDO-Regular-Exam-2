pipeline {
    agent any

    environment {
        DOTNET_VERSION = '8.0.x'
    }

    stages {

         stage('Setup .NET') {
            steps {
            script {
                sh "curl -sSL https://dotnetcli.azureedge.net/dotnet/Sdk/${DOTNET_VERSION}/dotnet-sdk-${DOTNET_VERSION}-linux-x64.tar.gz -o dotnet-sdk-${DOTNET_VERSION}-linux-x64.tar.gz"
                sh "mkdir -p $HOME/dotnet"
                sh "tar zxf dotnet-sdk-${DOTNET_VERSION}-linux-x64.tar.gz -C $HOME/dotnet"
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
