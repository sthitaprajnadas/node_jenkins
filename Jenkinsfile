pipeline {
  agent any
    
  tools {nodejs "mynode"}

    
  stages {
/* 	stage('Git') {
		git 'https://github.com/sthitaprajnadas/node_jenkins.git'
	} */
	stage('Build') {
		sh 'npm install'
	}
	stage('Test') {
		sh 'npm test'
	}     
  }
}
