@Library("Shared_lib") _

def runPipeline(){
     echo "$name"
}
pipeline {
    agent any

    stages {
     
        stage('Pass property'){
            steps{
                script{
                     if(BRANCH_NAME == 'develop'){
                          // Access dev config 
                         def devConfig = load "property/dev.groovy"
                         runPipeline() 
                     }
                }
            }
        }
    }
}
