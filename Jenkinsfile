pipeline{
  agent any
  stages{
    stage ('Git Cloning'){
    steps{
      script{
    git branch: 'main', url: 'https://github.com/zorif22/demo-project.git'
        }
      }
    }
    stage('unit test'){
      steps{
       script{
      sh 'mvn test'

}
}
}
}
}
}
