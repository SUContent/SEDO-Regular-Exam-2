pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')
    }

    stages {
        stage('Restore dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build the project') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }

        stage('Run the tests') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }

    post {
        success {
            echo "Build and tests passed successfully!"
        }
        failure {
            echo "Build or tests failed. Check the logs."
        }
    }
}
