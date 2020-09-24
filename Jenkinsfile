pipeline {
  agent any
  stages {
    stage("restore packages") {
      steps {
        bat '"C:\tools\nuget.exe" restore SeleniumNUnitParam.sln'
      }
    }
    stage("Build") {
      bat "\"${tool 'MSBuild'}\" SeleniumNUnitParam.sln /p:Configuration=Debug /p:Platform=\"Any CPU\""
    }
    stage("Test") {
      bat "C:\tools\nunit-console-runner\tools\nunit3-console.exe SeleniumNUnitParam/bin/Debug/SeleniumNunitParam.dll"
    }
  }
}
    
