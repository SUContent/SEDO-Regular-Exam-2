pipeline {
  agent { label 'ubuntu' }
  
  stages{
    stage('Restore dependencies') {
       bat dotnet restore
    }
    stage('Build') {
      bat dotnet build --no-restore
    }

    stage('Run Tests') {
      bat dotnet test --no-build --verbosity normal
    }
  }
}
