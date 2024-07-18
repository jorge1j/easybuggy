pipeline{
    agent any
	
    tools{
        maven "Maven_3_5_2"
	sonarqubeScanner 'Sonarqube'    
    }
	environment {
		SONARQUBE_SCANNER_HOME = tool name: 'sonarqube Scanner',
	type: 'hudson.plugins.sonar.SonarRunnerInstallation'
	}
     stages{
         stage('SonarQube Analysis') {
            steps {
                    withSonarQubeEnv('Sonarqube') { // 'SonarQube' should match the name configured in Jenkins
                        sh '${env.SONARQUBE_SCANNER_HOME}/bin/sonar-scanner"
                    }
                }
            }
        
	  //   stage('RunSCAAnalysisUsingSnyk') {
   //             steps {		
	  //         withCredentials([string(credentialsId: 'SNYK_TOKEN', variable: 'SNYK_TOKEN')]) {
			// 		sh 'mvn snyk:test -fn'
			// 	}
			// }
   //  }	
   //      stage('Build'){
   //          steps{
   //              withDockerRegistry(
   //                  [credentialsId:"dockerlogin", url: ""]
   //              )  {
   //                  script{
   //                  app = docker.build("asg")
   //                  }
   //              }
   //          }
   //      }

   //      stage('Push'){
   //          steps{
   //              script{
   //                  docker.withRegistry("https://924338258393.dkr.ecr.us-east-1.amazonaws.com", "ecr:us-east-1:aws-credentials"){
   //                      app.push("latest")
   //                  }
                    
                    
   //              }
   //          }
   //      }
    }

     }
}

