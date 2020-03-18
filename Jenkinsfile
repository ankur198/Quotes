pipeline {
  agent any
  stages {
    stage('Docker build') {
      steps {
        sh '''ls 

cd ./Quotes.Api/

docker build .'''
      }
    }

  }
}