pipeline {
  agent any
  stages {
    stage('Docker build') {
      steps {
        sh """
          cd ./Quotes.Api/

          docker build -t ${getImageName} .

          docker ps -a

          """
      }
    }

    stage('archive') {
      steps {
        sh "echo ${env.BUILD_TAG}"
        sh "docker tag  ${getImageName} localhost:5000/${getImageName}"
        sh "docker push localhost:5000/${getImageName}"
      }
    }

  }
}

def getImageName "quoteapidev:${env.BUILD_ID}"
