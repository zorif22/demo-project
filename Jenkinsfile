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
   }
}
