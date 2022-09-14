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

  }
}