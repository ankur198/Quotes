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
        sh "docker login -u ankur198 -p 31ac2f40-72ab-4fb3-9761-b8a758153f27
        sh "docker tag quotes:${getImageName} ${registryIP}:${getImageName}"
        sh "docker push ${registryIP}:${getImageName}"
      }
    }

  }
}
