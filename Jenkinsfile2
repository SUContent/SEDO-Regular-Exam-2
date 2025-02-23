pipeline {
    agent any

    // Poll SCM every 5 minutes
    triggers {
        pollSCM('H/5 * * * *')
    }

    environment {
        DOTNET_VERSION = '8.0.x' // Define .NET version for consistency
    }

    stages {

        stage('Checkout Repository') {
            steps {
                script {
                    echo 'Checking out the repository...'
                }
                checkout scm
            }
        }

        stage('Set up .NET Core') {
            steps {
                script {
                    echo 'Setting up .NET Core SDK...'
                }
                bat 'dotnet --version' // Ensure .NET is installed and accessible
            }
        }

        stage('Restore Dependencies') {
            steps {
                script {
                    echo 'Restoring dependencies...'
                }
                bat 'dotnet restore Horizons.sln' // Restore NuGet packages
            }
        }

        stage('Build') {
            steps {
                script {
                    echo 'Building the solution...'
                }
                bat 'dotnet build Horizons.sln --no-restore' // Build without restoring dependencies again
            }
        }

        stage('Run Tests in Parallel') {
            parallel {
                stage('Run Unit Tests') {
                    steps {
                        script {
                            echo 'Running Unit Tests...'
                        }
                        bat 'dotnet test Horizons.Tests.Unit/Horizons.Tests.Unit.csproj --no-build --verbosity normal || exit 1'
                    }
                }
                stage('Run Integration Tests') {
                    steps {
                        script {
                            echo 'Running Integration Tests...'
                        }
                        bat 'dotnet test Horizons.Tests.Integration/Horizons.Tests.Integration.csproj --no-build --verbosity normal || exit 1'
                    }
                }
            }
        }
    }

    post {
        success {
            echo '✅ Pipeline executed successfully!'
        }
        failure {
            echo '❌ Pipeline failed. Check logs for details.'
            script {
                currentBuild.result = 'FAILURE'
            }
        }
        aborted {
            echo '⚠️ Pipeline execution was aborted.'
        }
    }
}