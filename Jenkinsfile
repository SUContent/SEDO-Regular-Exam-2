pipeline {
    agent any

    environment {
        DOTNET_ROOT = 'C:\\Program Files\\dotnet'
        PATH = "C:\\Program Files\\dotnet;${env.PATH}"
    }


    stages {


        stage('Restore') {
            steps {
                sh 'dotnet restore'
            }
        }

           stage('Build') {
            steps {
                sh 'dotnet build --no-restore'
            }
        }

           stage('Test') {
            steps {
                sh 'dotnet test --no-build --verbosity-normal'
            }
        }
    }
}