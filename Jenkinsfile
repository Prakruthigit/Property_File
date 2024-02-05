pipeline {
    agent any

    stages {
        stage('Read Properties') {
            steps {
                script {
                    if (BRANCH_NAME == 'develop'){
                        def configFile = 'pipeline-properties/dev.properties'
                        def propertiesMap = [:]
                    } else if (BRANCH_NAME == 'qa'){
                         def configFile = 'pipeline-properties/qa.properties'
                        def propertiesMap = [:]      
                    }
                    

                    // Read the file content
                    def fileContent = readFile(file: configFile).trim()

                    // Split lines and iterate through them
                    fileContent.eachLine { line ->
                        // Split each line into key and value
                        def (key, value) = line.split('=')

                        // Trim whitespaces
                        key = key.trim()
                        value = value.trim()

                        // Add to properties map
                        propertiesMap[key] = value
                    }

                    // Now propertiesMap contains the key-value pairs
                    echo "Value of key1: ${propertiesMap['Monday']}"
                }
            }
        }
    }
}
