pipeline {
  agent any

  stages {
    stage {
      statage('Restore Dependances') {
        steps {
          bat 'dotnet restore'
        }
      }

      stage('Build') {
        steps {
          bat 'dotnet build --no-restore'
        }
      }

      stage('Run Tests') {
        steps {
          bat 'dotnet test =no-build --verbosity normal'
        }
      }
    }
  }
