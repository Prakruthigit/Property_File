pipeline {
    agent any

    stages {
        stage('Read Key-Value Pairs') {
            steps {
                script {
                    def branchName = env.BRANCH_NAME // Assuming you have the branch name available in env
                    def keyValues = [:]
                    def fileContent = sh(returnStdout: true, script: "git show ${branchName}:pipeline-properties/dev.properties")
                    
                    // Parse the file content to extract key-value pairs
                    fileContent.split('\n').each { line ->
                        def (key, value) = line.split('=')
                        keyValues[key.trim()] = value.trim()
                    }

                    // Now you have key-value pairs in keyValues map
                    echo "Key-Value pairs: ${keyValues}"
                }
            }
        }
    }
}
