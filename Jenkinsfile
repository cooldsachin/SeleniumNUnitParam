pipeline {
  agent any
  stages {
    stage("restore packages") {
      steps {
        bat '"C:\\tools\\nuget.exe" restore SeleniumNUnitParam.sln'
      }
    }
    stage("Build") {
      script {
          def msbuild = tool name: 'MSBuild', type: 'hudson.plugins.msbuild.MsBuildInstallation'
          bat "${msbuild} SeleniumNUnitParam.sln"
      } 
    }
    stage("Test") {
      steps {
        bat "C:\\tools\\nunit-console-runner\\tools\\nunit3-console.exe SeleniumNUnitParam/bin/Debug/SeleniumNunitParam.dll"
      }
    }
  }
}
    
