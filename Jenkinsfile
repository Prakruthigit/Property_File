pipeline {
    agent any

    stages {
        stage('Read Properties') {
            steps {
                script {
                    def propertiesMap = [:]
                    def configFile
                    def configFile2

                    if (BRANCH_NAME == 'develop') {
                        configFile = 'pipeline-properties/dev.properties'
                        configFile2 = 'pipeline-properties/dev2.properties'
                    } else if (BRANCH_NAME == 'qa') {
                        configFile = 'pipeline-properties/qa.properties'
                    } else {
                        error "Unsupported branch: ${BRANCH_NAME}"
                    }

                    // Read the file content
                    def fileContent = readFile(file: configFile).trim()
                    def fileContent2 = readFile(file: configFile2).trim()

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

                    fileContent2.eachLine { line ->
                        // Split each line into key and value
                        def (key2, value2) = line.split('=')

                        // Trim whitespaces
                        key2 = key2.trim()
                        value2 = value2.trim()

                        // Add to properties map
                        propertiesMap2[key2] = value2
                    }
                    

                    // Now propertiesMap contains the key-value pairs
                    echo "Value of key1: ${propertiesMap['Monday']}"
                    echo "Value of key1: ${propertiesMap2['Monday']}"
                }
            }
        }
    }
}
              
