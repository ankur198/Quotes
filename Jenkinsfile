pipeline {
  agent any
  stages {
    stage('Docker Image build') {
      steps {
        sh '''cd Quote.Api

docker build .'''
      }
    }

  }
}