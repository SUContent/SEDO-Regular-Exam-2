pipeline{
    agent any 
  
    stages{    

        stage("Checkout repository"){
            steps{
                checkout scm
            }
        }
      
        stage("Restore dependencies"){
            steps{
                bat "dotnet restore"
            }
        }

        stage("Build app"){
            steps{
                bat "dotnet build --no-restore"
            }
        }

        stage("Run unit and integration tests"){
            steps{
                bat "dotnet test --no-restore --verbosity normal"
            }
        }
                        
    }
}
