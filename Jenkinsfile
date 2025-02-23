pipeline {
    agent any

    stages {
        stage('Restore Dependencies') {
            steps {
                sh 'dotnet restore'
            }
        }

        stage('Build the application') {
            steps {
                sh 'dotnet build'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'dotnet test'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
