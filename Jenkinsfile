pipeline {
    agent any

    stages {
        stage('Install .NET 8.x.x') {
            steps {
                sh '''
                    # Install .NET 8.x.x if not already installed
                    if ! dotnet --list-sdks | grep -q "8"; then
                        wget https://download.visualstudio.microsoft.com/download/pr/56789abcdefg/dotnet-sdk-8.0.100-linux-x64.tar.gz -O /tmp/dotnet-sdk-8.0.100-linux-x64.tar.gz
                        mkdir -p /usr/share/dotnet
                        tar -zxf /tmp/dotnet-sdk-8.0.100-linux-x64.tar.gz -C /usr/share/dotnet
                        ln -s /usr/share/dotnet/dotnet /usr/bin/dotnet
                    fi
                '''
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

        stage('Run Tests') {
            steps {
                sh 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
