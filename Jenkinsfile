@Library("Shared_lib") _

def runPipeline(devConfig){
     echo "${property['Monday']}"
}
pipeline {
    agent any

    stages {
     
        stage('Pass property'){
            steps{
                script{
                     if(BRANCH_NAME == 'develop'){
                          // Access dev config 
                         def props = load('config/dev.groovy')
                          echo "${props.name}"
                     }
                }
            }
        }
    }
}
