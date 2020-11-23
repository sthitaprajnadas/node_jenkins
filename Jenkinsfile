pipeline {
  agent any
    
  tools {nodejs "mynode"}

    
  stages {

	stage('Build') {
		sh 'npm install'
	}
	stage('Test') {
		sh 'npm test'
	}     
  }
}
