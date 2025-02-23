pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Restore') {
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                bat 'dotnet build --configuration Release'
            }
        }

        stage('Test') {
            parallel {
                stage('Unit Tests') {
                    steps {
                        bat 'dotnet test Horizons.Tests.Unit/Horizons.Tests.Unit.csproj --configuration Release --no-build'
                    }
                }
                stage('Integration Tests') {
                    steps {
                        bat 'dotnet test Horizons.Tests.Integration/Horizons.Tests.Integration.csproj --configuration Release --no-build'
                    }
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