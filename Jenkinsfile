pipeline {
 agent any
  stages {
     stage('Checkout') {
            checkout scm
     }
    stage ('Build') {
     steps {
      echo 'Running Build Automation '
       sh './gradlew build --no-daemon'
       archiveArtifacts artifacts: 'dist/sampleapp.zip'
      
      stage ('Image Build') {
      steps {
       sh 'sudo docker build -t priyakarth/sampleapp .'
       sh 'sudo docker push priyakarth/jnekins'
      }
      }
        }
       }
      }
    }
