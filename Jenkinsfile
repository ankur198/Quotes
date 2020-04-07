String getImageName = env.BUILD_ID
String registryIP = "ankur198/quotes"

pipeline {
  agent any
  stages {
    stage('Restore') {
      steps {
        sh """
                          cd ./Quotes.Api/

                          dotnet restore

                          """
      }
    }
  }
}

