pipeline {
  agent any
  stages {
    stage('Restore') {
      steps {
        sh '''
                          cd ./Quotes.Api/

                          dotnet restore
                          
                          whoami

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
                          dotnet sonarscanner begin                             /k:Quotes                             /d:sonar.host.url=http://localhost:9000                             /d:sonar.login=0416f77efe7a8613d44305ad686548faee17e245
        

'''
        sh 'dotnet build'
        sh 'dotnet sonarscanner end /d:sonar.login=0416f77efe7a8613d44305ad686548faee17e245'
      }
    }

  }
}
