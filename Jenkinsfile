pipeline {
  agent any
  stages {
    stage('Restore') {
      steps {
        sh 'dotnet restore'
      }
    }

    stage('Start Analysis'){
      steps{
        sh 'dotnet sonarscanner begin /k:Quotes /d:sonar.host.url=http://localhost:9000 /d:sonar.login=0416f77efe7a8613d44305ad686548faee17e245'
      }
    }

    stage('Build') {
      steps {
        sh 'dotnet build'
      }
    }

    stage('End Analysis') {
      steps {
        sh 'dotnet sonarscanner end /d:sonar.login=0416f77efe7a8613d44305ad686548faee17e245'
      }
    }

  }
}
