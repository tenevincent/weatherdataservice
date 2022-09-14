pipeline {
  agent any
  stages {
    stage('Clean workspace') {
      steps {
        sh ' cleanWs()'
      }
    }

    stage('Clone  Repo') {
      steps {
        sh 'sh "git clone https://github.com/tenevincent/weatherdataservice.git"'
      }
    }

    stage('restore') {
      steps {
        sh 'sh "dotnet restore"'
      }
    }

    stage('build') {
      steps {
        sh 'sh "dotnet build"'
      }
    }

    stage('test') {
      steps {
        sh '''           dir("simple-dotnet-maven-app"){
                sh "dotnet test"
            }'''
        }
      }

    }
  }