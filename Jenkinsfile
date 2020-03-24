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
      }
    }
    stage("Docker login"){
        steps{
            echo "====++++executing Docker login++++===="
            sh "docker login -u ankur198 -p 31ac2f40-72ab-4fb3-9761-b8a758153f27"
        }
        post{
            success{
                echo "====++++Docker login executed succesfully++++===="
            }
            failure{
                echo "====++++Docker login execution failed++++===="
            }
    
        }
    }
    stage("Docker push"){
        steps{
            script{
              if($env.BRANCH_NAME=="master"){
                  echo "====++++executing Docker push++++===="
                  sh "docker tag quotes:${getImageName} ${registryIP}:${getImageName}"
                  sh "docker push ${registryIP}:${getImageName}"
              }
              else {
                echo "====++++Skipped push++++===="
              }
            }
        }
        // post{
        //     success{
        //         echo "====++++Docker push executed succesfully++++===="
        //     }
        //     failure{
        //         echo "====++++Docker push execution failed++++===="
        //     }
        // }
    }
  }
}

