pipeline {
    agent any

    environment {
        DOTNET_VERSION = "8.0.x"
    }
        stage('Restore Dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build Application') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }

        stage('Run Integration Tests') {
            steps {
                bat 'dotnet test Horizons.Tests.Integration/Horizons.Tests.Integration.csproj --no-build --logger "trx;LogFileName=test-results.trx" --results-directory TestResults'
            }
        }
    }

    post {
        always {
            script {
                def resultsExist = fileExists('TestResults/test-results.trx')
                if (resultsExist) {
                    echo '✅ Test results found, archiving...'
                    archiveArtifacts artifacts: 'TestResults/*.trx', fingerprint: true
                    junit 'TestResults/*.trx'
                } else {
                    echo '⚠️ No test results found!'
                }
            }
        }
    }
}

def isDotnetInstalled() {
    def output = bat(script: 'dotnet --version', returnStatus: true)
    return output == 0
}
