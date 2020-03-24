String getImageName = env.BUILD_ID
String registryIP = "ankur198/quotes"

pipeline {
  agent any
  stages {
    stage('Docker build') {
      steps {
        sh """
                          cd ./Quotes.Api/

                          docker build -t quotes:${getImageName} .

                          docker images

                          """
        sh "docker tag quotes:${getImageName} ${registryIP}:${getImageName}"
        sh "docker push ${registryIP}:${getImageName}"
      }
    }

  }
}
