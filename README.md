Successful build and test in Jenkins with Jenkins file by SCM change. Console output attached below:

Started by an SCM change
Obtained Jenkinsfile from git https://github.com/justBeroe/Horizons
[Pipeline] Start of Pipeline
[Pipeline] node
Running on Jenkins in C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Declarative: Checkout SCM)
[Pipeline] checkout
Selected Git installation does not exist. Using Default
The recommended git tool is: NONE
No credentials specified
 > git.exe rev-parse --resolve-git-dir C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\.git # timeout=10
Fetching changes from the remote Git repository
 > git.exe config remote.origin.url https://github.com/justBeroe/Horizons # timeout=10
Fetching upstream changes from https://github.com/justBeroe/Horizons
 > git.exe --version # timeout=10
 > git --version # 'git version 2.47.1.windows.1'
 > git.exe fetch --tags --force --progress -- https://github.com/justBeroe/Horizons +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git.exe rev-parse "refs/remotes/origin/feature-ci-pipeline^{commit}" # timeout=10
Checking out Revision 3274d9c8907c630f8b3019130d072ef61b4ef530 (refs/remotes/origin/feature-ci-pipeline)
 > git.exe config core.sparsecheckout # timeout=10
 > git.exe checkout -f 3274d9c8907c630f8b3019130d072ef61b4ef530 # timeout=10
Commit message: "Task 5 - Configure Jenkins [update Jenkinsfile test]"
 > git.exe rev-list --no-walk 2c05a5e5d68677cacf7a5cf707022575fcdf341a # timeout=10
[Pipeline] }
[Pipeline] // stage
[Pipeline] withEnv
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Restore dependencies)
[Pipeline] bat

C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile>dotnet restore 
  Determining projects to restore...
  All projects are up-to-date for restore.
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Build project)
[Pipeline] bat

C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile>dotnet build --no-restore 
  Horizons.Data -> C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Data\bin\Debug\net8.0\Horizons.Data.dll
C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons\Services\DestinationService.cs(108,47): warning CS8600: Converting null literal or possible null value to non-nullable type. [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons\Horizons.csproj]
C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons\Services\DestinationService.cs(120,39): warning CS8600: Converting null literal or possible null value to non-nullable type. [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons\Horizons.csproj]
C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons\Services\DestinationService.cs(135,29): warning CS8601: Possible null reference assignment. [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons\Horizons.csproj]
C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons\Services\DestinationService.cs(218,33): warning CS8601: Possible null reference assignment. [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons\Horizons.csproj]
  Horizons -> C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons\bin\Debug\net8.0\Horizons.dll
C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\IntegrationTests.cs(102,51): warning CS8602: Dereference of a possibly null reference. [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\Horizons.Tests.Integration.csproj]
C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Unit\UnitTests.cs(134,13): warning NUnit2005: Consider using the constraint model, Assert.That(actual, Is.EqualTo(expected)), instead of the classic model, Assert.AreEqual(expected, actual) (https://github.com/nunit/nunit.analyzers/tree/master/documentation/NUnit2005.md) [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Unit\Horizons.Tests.Unit.csproj]
C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\IntegrationTests.cs(99,13): warning NUnit2005: Consider using the constraint model, Assert.That(actual, Is.EqualTo(expected)), instead of the classic model, Assert.AreEqual(expected, actual) (https://github.com/nunit/nunit.analyzers/tree/master/documentation/NUnit2005.md) [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\Horizons.Tests.Integration.csproj]
C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Unit\UnitTests.cs(81,13): warning NUnit2005: Consider using the constraint model, Assert.That(actual, Is.EqualTo(expected)), instead of the classic model, Assert.AreEqual(expected, actual) (https://github.com/nunit/nunit.analyzers/tree/master/documentation/NUnit2005.md) [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Unit\Horizons.Tests.Unit.csproj]
C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\IntegrationTests.cs(63,13): warning NUnit2005: Consider using the constraint model, Assert.That(actual, Is.EqualTo(expected)), instead of the classic model, Assert.AreEqual(expected, actual) (https://github.com/nunit/nunit.analyzers/tree/master/documentation/NUnit2005.md) [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\Horizons.Tests.Integration.csproj]
C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Unit\UnitTests.cs(109,13): warning NUnit2005: Consider using the constraint model, Assert.That(actual, Is.EqualTo(expected)), instead of the classic model, Assert.AreEqual(expected, actual) (https://github.com/nunit/nunit.analyzers/tree/master/documentation/NUnit2005.md) [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Unit\Horizons.Tests.Unit.csproj]
C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\IntegrationTests.cs(102,13): warning NUnit2005: Consider using the constraint model, Assert.That(actual, Is.EqualTo(expected)), instead of the classic model, Assert.AreEqual(expected, actual) (https://github.com/nunit/nunit.analyzers/tree/master/documentation/NUnit2005.md) [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\Horizons.Tests.Integration.csproj]
C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\IntegrationTests.cs(66,13): warning NUnit2005: Consider using the constraint model, Assert.That(actual, Is.EqualTo(expected)), instead of the classic model, Assert.AreEqual(expected, actual) (https://github.com/nunit/nunit.analyzers/tree/master/documentation/NUnit2005.md) [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\Horizons.Tests.Integration.csproj]
C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\IntegrationTests.cs(103,13): warning NUnit2005: Consider using the constraint model, Assert.That(actual, Is.EqualTo(expected)), instead of the classic model, Assert.AreEqual(expected, actual) (https://github.com/nunit/nunit.analyzers/tree/master/documentation/NUnit2005.md) [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\Horizons.Tests.Integration.csproj]
C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\IntegrationTests.cs(67,13): warning NUnit2005: Consider using the constraint model, Assert.That(actual, Is.EqualTo(expected)), instead of the classic model, Assert.AreEqual(expected, actual) (https://github.com/nunit/nunit.analyzers/tree/master/documentation/NUnit2005.md) [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\Horizons.Tests.Integration.csproj]
  Horizons.Tests.Integration -> C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\bin\Debug\net8.0\Horizons.Tests.Integration.dll
  Horizons.Tests.Unit -> C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Unit\bin\Debug\net8.0\Horizons.Tests.Unit.dll

Build succeeded.

C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons\Services\DestinationService.cs(108,47): warning CS8600: Converting null literal or possible null value to non-nullable type. [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons\Horizons.csproj]
C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons\Services\DestinationService.cs(120,39): warning CS8600: Converting null literal or possible null value to non-nullable type. [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons\Horizons.csproj]
C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons\Services\DestinationService.cs(135,29): warning CS8601: Possible null reference assignment. [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons\Horizons.csproj]
C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons\Services\DestinationService.cs(218,33): warning CS8601: Possible null reference assignment. [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons\Horizons.csproj]
C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\IntegrationTests.cs(102,51): warning CS8602: Dereference of a possibly null reference. [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\Horizons.Tests.Integration.csproj]
C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Unit\UnitTests.cs(134,13): warning NUnit2005: Consider using the constraint model, Assert.That(actual, Is.EqualTo(expected)), instead of the classic model, Assert.AreEqual(expected, actual) (https://github.com/nunit/nunit.analyzers/tree/master/documentation/NUnit2005.md) [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Unit\Horizons.Tests.Unit.csproj]
C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\IntegrationTests.cs(99,13): warning NUnit2005: Consider using the constraint model, Assert.That(actual, Is.EqualTo(expected)), instead of the classic model, Assert.AreEqual(expected, actual) (https://github.com/nunit/nunit.analyzers/tree/master/documentation/NUnit2005.md) [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\Horizons.Tests.Integration.csproj]
C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Unit\UnitTests.cs(81,13): warning NUnit2005: Consider using the constraint model, Assert.That(actual, Is.EqualTo(expected)), instead of the classic model, Assert.AreEqual(expected, actual) (https://github.com/nunit/nunit.analyzers/tree/master/documentation/NUnit2005.md) [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Unit\Horizons.Tests.Unit.csproj]
C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\IntegrationTests.cs(63,13): warning NUnit2005: Consider using the constraint model, Assert.That(actual, Is.EqualTo(expected)), instead of the classic model, Assert.AreEqual(expected, actual) (https://github.com/nunit/nunit.analyzers/tree/master/documentation/NUnit2005.md) [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\Horizons.Tests.Integration.csproj]
C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Unit\UnitTests.cs(109,13): warning NUnit2005: Consider using the constraint model, Assert.That(actual, Is.EqualTo(expected)), instead of the classic model, Assert.AreEqual(expected, actual) (https://github.com/nunit/nunit.analyzers/tree/master/documentation/NUnit2005.md) [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Unit\Horizons.Tests.Unit.csproj]
C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\IntegrationTests.cs(102,13): warning NUnit2005: Consider using the constraint model, Assert.That(actual, Is.EqualTo(expected)), instead of the classic model, Assert.AreEqual(expected, actual) (https://github.com/nunit/nunit.analyzers/tree/master/documentation/NUnit2005.md) [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\Horizons.Tests.Integration.csproj]
C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\IntegrationTests.cs(66,13): warning NUnit2005: Consider using the constraint model, Assert.That(actual, Is.EqualTo(expected)), instead of the classic model, Assert.AreEqual(expected, actual) (https://github.com/nunit/nunit.analyzers/tree/master/documentation/NUnit2005.md) [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\Horizons.Tests.Integration.csproj]
C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\IntegrationTests.cs(103,13): warning NUnit2005: Consider using the constraint model, Assert.That(actual, Is.EqualTo(expected)), instead of the classic model, Assert.AreEqual(expected, actual) (https://github.com/nunit/nunit.analyzers/tree/master/documentation/NUnit2005.md) [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\Horizons.Tests.Integration.csproj]
C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\IntegrationTests.cs(67,13): warning NUnit2005: Consider using the constraint model, Assert.That(actual, Is.EqualTo(expected)), instead of the classic model, Assert.AreEqual(expected, actual) (https://github.com/nunit/nunit.analyzers/tree/master/documentation/NUnit2005.md) [C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\Horizons.Tests.Integration.csproj]
    14 Warning(s)
    0 Error(s)

Time Elapsed 00:00:07.58
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Run dotnet tests)
[Pipeline] bat

C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile>dotnet test --no-build --verbosity normal 
Build started 2/23/2025 10:00:19 AM.
     1>Project "C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.sln" on node 1 (VSTest target(s)).
     1>ValidateSolutionConfiguration:
         Building solution configuration "Debug|Any CPU".
Test run for C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Unit\bin\Debug\net8.0\Horizons.Tests.Unit.dll (.NETCoreApp,Version=v8.0)
Test run for C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\bin\Debug\net8.0\Horizons.Tests.Integration.dll (.NETCoreApp,Version=v8.0)
VSTest version 17.12.0 (x64)
VSTest version 17.12.0 (x64)


Starting test execution, please wait...
Starting test execution, please wait...
A total of 1 test files matched the specified pattern.
A total of 1 test files matched the specified pattern.
NUnit Adapter 4.2.0.0: Test execution started
NUnit Adapter 4.2.0.0: Test execution started
Running all tests in C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Integration\bin\Debug\net8.0\Horizons.Tests.Integration.dll
Running all tests in C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.Tests.Unit\bin\Debug\net8.0\Horizons.Tests.Unit.dll
   NUnit3TestExecutor discovered 2 of 2 NUnit test cases using Current Discovery mode, Non-Explicit run
   NUnit3TestExecutor discovered 4 of 4 NUnit test cases using Current Discovery mode, Non-Explicit run
NUnit Adapter 4.2.0.0: Test execution complete
NUnit Adapter 4.2.0.0: Test execution complete
  Passed AddDestination_ShouldInsertDestinationIntoDatabase [750 ms]
  Passed EditDestination_ShouldUpdateDestinationInDatabase [56 ms]

  Passed Add_Get_ShouldReturnViewWithTerrains [636 ms]
  Passed Add_Post_ShouldRedirectToIndex_OnValidModel [88 ms]
  Passed AddToFavorites_ShouldRedirectToIndex_WhenDestinationIsAdded [62 ms]
  Passed Edit_Get_ShouldReturnViewWithCorrectModel_WhenDestinationExists [20 ms]

Test Run Successful.
Total tests: 2
     Passed: 2
Test Run Successful.
Total tests: 4
     Passed: 4
 Total time: 1.4133 Seconds
 Total time: 1.4177 Seconds
     1>Done Building Project "C:\Users\up636306\AppData\Local\Jenkins\.jenkins\workspace\Horizons-Exam23Feb05-Jenkinsfile\Horizons.sln" (VSTest target(s)).

Build succeeded.
    0 Warning(s)
    0 Error(s)

Time Elapsed 00:00:02.38
[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // node
[Pipeline] End of Pipeline
Finished: SUCCESS
