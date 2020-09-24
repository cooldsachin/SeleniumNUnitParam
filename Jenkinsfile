pipeline {
  agent any
  {
  stages {
    stage("restore packages") {
      steps {
        bat '"C:\tools\nuget.exe" restore SeleniumNUnitParam.sln'
      }
    }
    stage("")
