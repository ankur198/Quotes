pipeline {
  agent any
  stages {
    stage('Docker Image build') {
      steps {
        sh 'scm checkout'
        sh '''cd Quote.Api

docker build .'''
      }
    }

  }
}