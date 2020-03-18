pipeline {
  agent any
  stages {
    stage('Docker build') {
      steps {
        sh '''ls 

cd ./Quotes.Api/

docker build .

docker ps -a'''
      }
    }

    stage('archive') {
      steps {
        sh 'docker ps -a'
      }
    }

  }
}