pipeline {
  agent any 
  stages {
    stage('Example') {
      steps {
        script{
           def Config = load('pipeline-properties/dev.groovy')
           echo "${Config['name']}"
        }
      }
    }
  }
}
