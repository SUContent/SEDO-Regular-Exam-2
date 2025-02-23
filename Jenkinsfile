properties([
    pipelineTriggers([[$class: 'GitHubPushTrigger']])
])

node {
    stage('Define env variables'){ 
        env.PATH_TO_PROJECT_FILE = "C:\\Users\\jenkins\\Documents\\Horizons\\Horizons.sln"
        env.PATH_TO_UNIT_TESTS = "C:\\Users\\jenkins\\Documents\\Horizons\\Horizons.Tests.Unit\\Horizons.Tests.Unit.csproj"
        env.PATH_TO_INTEGRATION_TESTS = "C:\\Users\\jenkins\\Documents\\Horizons\\Horizons.Tests.Integration\\Horizons.Tests.Integration.csproj"
    }

    stage('Clean the Working Space') {
        cleanWs()
    }

    stage('Restore Project Packages') {
        bat "dotnet restore %PATH_TO_PROJECT_FILE%"
        echo "Package restore done!"
    }

    stage('Build the Project') {
        bat "dotnet build %PATH_TO_PROJECT_FILE%"
        echo "Project build done!"
    }

    stage('Run Both Integration and Unit Tests when push event on branch feature-ci-pipeline') {
        bat """
        dotnet test %PATH_TO_UNIT_TESTS% --configuration Release
        dotnet test %PATH_TO_INTEGRATION_TESTS% --configuration Release
        echo Tests completed!
        """
    }
}