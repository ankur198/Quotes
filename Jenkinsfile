pipeline {
  agent any
  stages {
    stage('Docker build') {
      steps {
        sh """
          cd ./Quotes.Api/

          docker build -t quoteapidev:${env.BUILD_ID} .

          docker ps -a

          """
      }
    }

    stage('archive') {
      steps {
        sh "echo ${env.BUILD_TAG}"
        sh "docker tag  quoteApiDev:${env.BUILD_ID} localhost:5000/quoteApiDev:${env.BUILD_ID}"
        sh "docker push localhost:5000/quoteApiDev:${env.BUILD_ID}"
      }
    }

  }
}