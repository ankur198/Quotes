pipeline {
  agent any
  stages {
    stage('Docker build') {
      steps {
        sh '''ls 

cd ./Quote.Api/

docker build .'''
      }
    }

  }
}