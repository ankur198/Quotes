pipeline {
  agent any
  stages {
    stage('clone'){
      steps{
        scm checkout
      }
    }
    stage('Docker Image build') {
      steps {
        sh '''cd Quote.Api
              docker build .'''
      }
    }

  }
}