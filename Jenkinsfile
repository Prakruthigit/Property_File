// Jenkinsfile

def readFileContent(filePath) {
    try {
        return readFile(filePath).trim()
    } catch (Exception e) {
        error "Failed to read file: ${filePath}, error: ${e.message}"
    }
}

pipeline {
    agent any
    
    stages {
        stage('Read File') {
            steps {
                script {
                    // Specify the path to the file you want to read
                    def filePath = 'pipeline-properties/dev.properties'
                    
                    // Call the custom function to read the file content
                    def fileContent = readFileContent(filePath)
                    
                    // Print the content or use it as needed
                    echo "File Content: ${fileContent}"
                }
            }
        }
        
        // Add more stages as needed
    }
    
    // Post-build actions, etc.
}
