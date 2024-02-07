def runPipeline(keyValues){
     echo "Value of key1: ${keyValues['Monday']}"
}

pipeline {
    agent any

    stages {
        stage('Read Property File') {
            steps {
                script {
                    if (BRANCH_NAME == 'develop'){
                        // Define a shell command to read the property file
                    def command = "cat pipeline-properties/dev.properties"
                    }
                    
                    // Execute the shell command
                    def fileContent = sh(script: command, returnStdout: true).trim()
                    
                    // Split file content by newline and parse key-value pairs
                    def keyValues = [:]
                    fileContent.split('\n').each { line ->
                        def (key, value) = line.tokenize('=')
                        keyValues[key.trim()] = value.trim()
                    }
                    
                    // Accessing properties
                    //def key1 = keyValues['key1']
                    //def key2 = keyValues['key2']
                   
                }
            }
        }

        stage('Pass property'){
            steps{
                script{
                    runPipeline(keyValues)
                }
            }
        }
    }
}
