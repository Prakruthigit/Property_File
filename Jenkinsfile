pipeline {
    agent any

    environment {
        BRANCH_NAME = sh(script: 'git rev-parse --abbrev-ref HEAD', returnStdout: true).trim()
    }

    stages {
        stage('Read Properties') {
            steps {
                script {
                    def propertiesMap = [:]
                    def configFile

                    if (BRANCH_NAME == 'develop') {
                        configFile = 'path/to/dev.properties'
                    } else if (BRANCH_NAME == 'qa') {
                        configFile = 'path/to/qa.properties'
                    } else {
                        error "Unsupported branch: ${BRANCH_NAME}"
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
                    echo "Value of key1: ${propertiesMap['branch_name']}"
                }
            }
        }
    }
}
