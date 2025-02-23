pipeline {
  agent any
  stages {
    stage('Build Horizons Project') {
      steps {
        bat 'dotnet build'
      }
    }
    stage('Run all test') {
      steps {
        bat 'dotnet test'
      }
    }
  }
}