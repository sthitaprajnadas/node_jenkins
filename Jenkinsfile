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
		git 'https://github.com/sthitaprajnadas/node_jenkins'
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
