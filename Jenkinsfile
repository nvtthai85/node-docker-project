pipeline {
  agent any 
  stages {
    stage("Checkout"){
      steps{
        checkout scm
      }
    }
    
    stage ("Test"){
      steps{
        sh 'npm test'
      }
    }

    stage ("Build"){
      steps{
        sh 'npm run build'
      }
    }
  }
}
