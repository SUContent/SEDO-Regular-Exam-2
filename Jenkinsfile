pipeline {
    agent any
        triggers {
        githubPush()
    }
    environment {
        DOTNET_VERSION = '8.0'  // .NET version 8
        SOLUTION_FILE = 'Horizons.sln'
    }

    stages {
        stage('Restore Dependencies') {
            steps {
                script {
                    echo '📦 Restoring NuGet packages...'
                    bat "dotnet restore ${SOLUTION_FILE}"
                }
            }
        }

        stage('Build Solution') {
            steps {
                script {
                    echo '🛠️ Building the project...'
                    bat "dotnet build ${SOLUTION_FILE} --configuration Release --no-restore"
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    echo '🧪 Running tests...'
                    bat "dotnet test ${SOLUTION_FILE} --logger trx --results-directory TestResults"
                }
            }
        }
    }

    post {
        success {
            echo '✅ Build and Tests Passed Successfully!'
        }
        failure {
            echo '❌ Build or Tests Failed! Check logs.'
        }
    }
}
