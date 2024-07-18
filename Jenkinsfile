pipeline {
    agent any
    
    environment {
        SONAR_TOKEN = credentials('sonarcloud-token') // Define your SonarCloud token here
        SNYK_TOKEN = credentials('snyk-token')       // Snyk API token
    }
    
    tools {
        maven 'Maven_3_5_3' // Use the name you defined in Global Tool Configuration
    }
    
    stages {
	  stage('SonarCloud Analysis') {
            steps {
                script {
                    // Run SonarCloud analysis
                    sh "mvn clean verify sonar:sonar -Dsonar.projectKey=your_project_key -Dsonar.organization=your_organization -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=${SONAR_TOKEN}"
                }
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

