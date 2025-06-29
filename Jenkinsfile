pipeline {
  agent any

  triggers {
    pollSCM('H/2 * * * *')  // Optional: fallback polling
  }

  environment {
    DOTNET_CLI_TELEMETRY_OPTOUT = '1'
    DOTNET_SKIP_FIRST_TIME_EXPERIENCE = '1'
    PATH = "/usr/share/dotnet:$PATH"
  }

  options {
    skipDefaultCheckout(true)
  }

  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }

    stage('Set up .NET SDK') {
      steps {
        // Assumes dotnet 8.0 is pre-installed on the Jenkins agent
        sh 'dotnet --version'
      }
    }

    stage('Restore dependencies') {
      steps {
        sh 'dotnet restore'
      }
    }

    stage('Build project') {
      steps {
        sh 'dotnet build --no-restore --configuration Release'
      }
    }

    stage('Run unit tests') {
      steps {
        sh 'dotnet vstest Horizons.Tests.Unit/Horizons.Tests.Unit.csproj'
      }
    }

    stage('Run integration tests') {
      steps {
        sh 'dotnet vstest Horizons.Tests.Integration/Horizons.Tests.Integration.csproj'
      }
    }
  }

  post {
    always {
      echo 'Pipeline complete.'
    }
    failure {
      echo 'Build or tests failed.'
    }
  }
}
