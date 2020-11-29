pipeline {
  environment {
	registry = 'dockerspd/jenkins-node-todo-frontend'
    registryCredential = 'dockerhub'
    dockerImage = ''
  }
  agent any
  stages {
    stage('Cloning Git') {
      steps {
		git branch: 'main',
            credentialsId: '2d815a95-a1c5-4081-93bc-9630e8e7dbe9',
        	url 'https://github.com/sthitaprajnadas/node_jenkins.git'
      }
    }
    stage('Building image') {
      steps{
        script {
          dockerImage = docker.build registry + ":$BUILD_NUMBER"
        }
      }
    }
    stage('Deploy Image') {
      steps{
        script {
          docker.withRegistry( '', registryCredential ) {
            dockerImage.push()
          }
        }
      }
    }
    stage('Remove Unused docker image') {
      steps{
        sh "docker rmi $registry:$BUILD_NUMBER"
      }
    }
  }
}
