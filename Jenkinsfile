@Library("Shared_lib") _

pipeline {
  agent any 
  stages {
    stage('Example') {
      steps {
        script{
           properties = readProperties file: 'pipeline-properties/dev.properties'   
           echo "${property['Monday']}"
        }
      }
    }
  }
}
