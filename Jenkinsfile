pipeline {
    agent any
    
    triggers {
        // Trigger builds when changes are pushed to main branch
        pollSCM('H/5 * * * *')
    }
    
    environment {
        DOTNET_CLI_HOME = "/tmp/DOTNET_CLI_HOME"
        DOTNET_SKIP_FIRST_TIME_EXPERIENCE = "1"
        DOTNET_NOLOGO = "1"
    }
    
    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code from main branch...'
                checkout scm
            }
        }
        
        stage('Setup .NET 8') {
            steps {
                echo 'Setting up .NET 8 SDK...'
                script {
                    if (isUnix()) {
                        sh '''
                            # Install .NET 8 SDK if not present
                            if ! command -v dotnet &> /dev/null; then
                                wget https://dot.net/v1/dotnet-install.sh -O dotnet-install.sh
                                chmod +x ./dotnet-install.sh
                                ./dotnet-install.sh --channel 8.0
                                export PATH="$PATH:$HOME/.dotnet"
                            fi
                            dotnet --version
                        '''
                    } else {
                        bat 'dotnet --version'
                    }
                }
            }
        }
        
        stage('Restore Dependencies') {
            steps {
                echo 'Restoring NuGet packages...'
                script {
                    if (isUnix()) {
                        sh 'dotnet restore'
                    } else {
                        bat 'dotnet restore'
                    }
                }
            }
        }
        
        stage('Build Application') {
            steps {
                echo 'Building .NET 8 application...'
                script {
                    if (isUnix()) {
                        sh 'dotnet build --no-restore --configuration Release'
                    } else {
                        bat 'dotnet build --no-restore --configuration Release'
                    }
                }
            }
        }
        
        stage('Execute All Tests') {
            steps {
                echo 'Running all tests...'
                script {
                    if (isUnix()) {
                        sh '''
                            dotnet test --no-build --configuration Release \
                                --logger "trx;LogFileName=TestResults.trx" \
                                --results-directory ./TestResults \
                                --verbosity normal
                        '''
                    } else {
                        bat '''
                            dotnet test --no-build --configuration Release ^
                                --logger "trx;LogFileName=TestResults.trx" ^
                                --results-directory ./TestResults ^
                                --verbosity normal
                        '''
                    }
                }
            }
            post {
                always {
                    // Publish test results
                    publishTestResults testResultsPattern: '**/TestResults/*.trx'
                    archiveArtifacts artifacts: '**/TestResults/**/*', allowEmptyArchive: true
                }
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline completed successfully! ✅'
            echo 'Application built and all tests executed on main branch push.'
        }
        failure {
            echo 'Pipeline failed! ❌'
        }
        always {
            cleanWs()
        }
    }
}