pipeline {
  agent any
  stages {
    stage('Restore') {
      steps {
        sh '''
                          cd ./Quotes.Api/

                          dotnet restore

                          '''
      }
    }

    stage('dotnet build') {
      steps {
        sh 'cd ./Quotes.api'
        sh 'dir'
      }
    }

  }
}