pipeline {

agent any

stages {

stage('Checkout') {

steps {

dir('cicd-pipeline-gradle') {

git credentialsId: 'GITHUB', url: 'https://github.com/priyakarth/cicd-pipeline-gradle'

}

}

}

stage ('Build') {

steps {

echo 'Running Build Automation '

sh './gradlew build --no-daemon'

archiveArtifacts artifacts: 'dist/sampleapp.zip'

}

}


stage ('Image Build') {

steps {

script {

sh "docker build -t priyakarth/sampleapp ."

}

}

}

}

} 
    

