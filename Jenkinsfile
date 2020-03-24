String getImageName = env.BUILD_ID
String registryIP = "ankur198/quotes"

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
        sh "docker tag ${getImageName} ${registryIP}/${getImageName}"
        sh "docker push ${registryIP}:${getImageName}"
      }
    }

  }
}
