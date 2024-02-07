// Jenkinsfile

def config = readProperties file: 'config.properties'
pipeline {

  agent any

  environment { 
    ENV = 'config.environment'
    API_URL = 'config.api_url' 
  }

  stages {
    stage('Example') {
      steps {
        sh 'echo $ENV'
        sh 'echo $API_URL' 
      }
    }
  }
}
