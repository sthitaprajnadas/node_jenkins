pipeline {
  agent any
    
  tools {nodejs "mynode"}

    
  stages {
    stage('checkout stage') {
     steps {
            git branch: 'main',
                credentialsId: '2d815a95-a1c5-4081-93bc-9630e8e7dbe9',
                url: 'https://github.com/sthitaprajnadas/node_jenkins.git'
            sh "ls -lat"
        }
        }
        

        
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
