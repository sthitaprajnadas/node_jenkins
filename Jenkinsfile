pipeline {
  agent any
    
  tools {nodejs "mynode"}

    
 stages {
         

        
    stage('Install dependencies') {
      steps {
        sh 'npm install'
      }
    }
     
    stage('Test') {
      steps {
         sh 'npm test'
      }
    }      
  }
}
