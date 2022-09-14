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

     stage("restore") {         
         steps {
            dir("simple-net-app"){
                sh "dotnet restore"
            }
         }
     }
	 
	      stage("build") {         
         steps {
            dir("simple-net-app"){
                sh "dotnet build"
            }
         }
     }
	 

     stage("Test") {         
         steps {
            dir("simple-dotnet-maven-app"){
                sh "dotnet test"
            }
         }
     }


  }
}

