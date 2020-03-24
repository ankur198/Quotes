pipeline {
  agent any
  stages {
    stage('Docker build') {
      steps {
        sh """
                  cd ./Quotes.Api/

                  docker build -t ${getImageName} .

                  docker images

                  """
      }
    }

    stage('archive') {
      steps {
        sh "docker tag  ${getImageName} localhost:5000/${getImageName}"
        sh "docker push localhost:5000/${getImageName}"
      }
    }

  }
}