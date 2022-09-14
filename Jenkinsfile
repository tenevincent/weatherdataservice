pipeline {

  agent any 

  stages {

     stage("Clean workspace") {         
         steps {
            cleanWs()
         }
     }
     
     stage("Clone  Repo") {         
         steps {
            sh "git clone https://github.com/tenevincent/weatherdataservice.git"
         }
     }

     stage("Restore") {         
         steps {
            dir("simple-net-app"){
                sh "dotnet restore  /var/jenkins_home/workspace/weatherdataservice-2_master/weatherdataservice/WeatherDataServiceApp.sln"
            }
         }
     }

   stage("Build") {         
         steps {
            dir("simple-net-app"){
                sh "dotnet build  /var/jenkins_home/workspace/weatherdataservice-2_master/weatherdataservice/WeatherDataServiceApp.sln"
            }
         }
     }


     stage("Test") {         
         steps {
            dir("simple-java-maven-app"){
                sh "dotnet test /var/jenkins_home/workspace/weatherdataservice-2_master/weatherdataservice/WeatherDataServiceApp.sln"
            }
         }
     }


  }
}

