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

    stage('Build') {
      steps {
        sh '''
                          cd ./Quotes.Api
                          
                          dotnet build
        '''
      }
    }
    stage('Analysis') {
      steps {
        sh '''
                          cd ./Quotes.Api
                          
                          sonar-scanner \
                            -Dsonar.projectKey=Quotes \
                            -Dsonar.sources=. \
                            -Dsonar.host.url=http://localhost:9000 \
                            -Dsonar.login=0416f77efe7a8613d44305ad686548faee17e245
        '''
      }
    }
  }
}
