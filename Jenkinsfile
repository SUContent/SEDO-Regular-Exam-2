// Pipeline description:
// This Jenkins pipeline is meant to be run locally (on the machine, currently testing the code)

pipeline {
    agent any

    // RECOMMENDED: '--no-restore' and '--no-build' statuses -> TRUE (by default)
    parameters {
        booleanParam(name: 'SWITCH_NO_RESTORE', defaultValue: true, description: 'Enable/Disable "--no-restore" option in "Stage 2. Build add".')
        booleanParam(name: 'SWITCH_NO_BUILD', defaultValue: true, description: 'Enable/Disable "--no-build" option in "Stage 3. Run all tests".')
    }
  
    stages {
        stage('1. Restore project dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }
    
        stage('2. Build app') {
            steps {
                script {
                    if (params.SWITCH_NO_RESTORE) {
                        bat 'dotnet build --no-restore'
                    } else {
                        bat 'dotnet build'
                    }
                }
            }
        }
    
        stage('3. Run all tests') {
            steps {
                script {
                    if (params.SWITCH_NO_BUILD) {
                        bat 'dotnet test --no-build --verbosity normal'
                    } else {
                        bat 'dotnet test --verbosity normal'
                    }
                }
            }
        }
    }
}
