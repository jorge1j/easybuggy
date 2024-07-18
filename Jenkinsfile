pipeline{
    agent any

    environment {
        SONARQUBE_URL = 'http://16.170.141.19:9000'
        SONARQUBE_TOKEN = credentials('SONAR_TOKEN') // Replace with your SonarQube token ID
       // MAVEN_HOME = tool name: 'Maven 3', type: 'maven' // Ensure this matches the Maven installation name in Jenkins
    }

    tools{
        maven "Maven_3_5_2"
    }
     stages{
         stage('SonarQube Analysis') {
            steps {
                script {
                    // Run SonarQube analysis
                    withSonarQubeEnv('SONAR') { // 'SonarQube' should match the name configured in Jenkins
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
}
}
