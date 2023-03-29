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
	satge('unit testing){
	  steps{
	    script{
		sh 'mvn test'
}	
}
}
	stages('Intigration testing'){
	 steps{
	   script{
		sh 'mvn verify'
          }	
        }
      }
    }	
}
