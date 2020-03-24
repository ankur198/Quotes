String getImageName = env.BUILD_ID
String registryIP = "172.18.0.4:5000"

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
        sh "docker push http://${registryIP}/${getImageName}"
      }
    }

  }
}
