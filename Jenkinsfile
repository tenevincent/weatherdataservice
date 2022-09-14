pipeline {
  agent any
  stages {
    stage('Clean workspace') {
      steps {
        cleanWs()
      }
    }

    stage('Clone  Repo') {
      steps {
        sh 'git clone https://github.com/tenevincent/weatherdataservice.git'
      }
    }

    stage('Restore') {
      steps {
        dir(path: 'simple-net-app') {
          sh 'dotnet restore  ${WORKSPACE}/weatherdataservice_master/weatherdataservice'
        }

      }
    }

    stage('Build') {
      steps {
        dir(path: 'simple-net-app') {
          sh 'dotnet build  ${workspace}/weatherdataservice_master/weatherdataservice'
        }

      }
    }

    stage('Test') {
      steps {
        dir(path: 'simple-java-maven-app') {
          sh 'dotnet test ${workspace}/weatherdataservice_master/weatherdataservice'
        }

      }
    }

  }
}