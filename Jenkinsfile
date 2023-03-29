pipeline{
  agent any
   stages{
    stage('Git Cloning'){
	steps{
	 script{
	git branch : 'main', url: 'https://github.com/zorif22/demo-project.git'
}
}	
}
	stage ('unit testing'){
	  steps{
	    script{
		sh 'mvn test'
}	
}
}
	stage('Intigration testing'){
	 steps{
	   script{
		sh 'mvn verify'
          }	
        }
      }
	   stage('Built'){
	 steps{
	   script{
		sh 'mvn clean install'
   }	
 }
}
	   stage('code quality'){
		   steps{
			   script{
			   withSonarQubeEnv(credentialsId: 'Jenkins') {
    			sh 'mvn clean package sonar:sonar'
	     }
	   }
	  }
      }
	   stage('upload to nexus'){
		   steps{
			   script{
			   nexusArtifactUploader artifacts: 
				   [
					   [artifactId: 'springboot', 
					    classifier: '', 
					    file: 'target/Uber.jar', 
					    type: 'jar']
				   ], 
				   credentialsId: '08f0d3b9-1df3-4ea4-854c-d724fe57f197', 
				   groupId: 'com.example', 
				   nexusUrl: '13.235.63.180:8081', 
				   nexusVersion: 'nexus3', 
				   protocol: 'http', 
				   repository: 'Demo_Project', 
				   version: '1.0.0'
			   }
		   }
	   }
   }
}
