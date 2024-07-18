pipeline{
    agent any 
    tools{
        maven "Maven_3_5_2"
    }
	enviroment{
		SONARQUBE_URL = 'http://16.170.141.19:9000/'
        SONARQUBE_TOKEN = credentials('JENKINS_SONAR_TOKEN1')
	}
     stages{
         stage('SonarQube Analysis') {
            steps {
                script {
                    // Run SonarQube analysis
                    withSonarQubeEnv('JENKINS_SONAR_TOKEN1') { // 'SonarQube' should match the name configured in Jenkins
                        sh 'mvn sonar:sonar'
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
