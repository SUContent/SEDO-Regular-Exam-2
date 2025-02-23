pipeline {
    agent any

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

        stage('Test Unit') {
            steps {
                sh 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
