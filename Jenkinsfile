pipeline {
    agent any

    stages {
        stage('Read Properties File') {
            steps {
                script {
                    // Specify the path to the properties file
                    def propertiesFilePath = 'pieline-propperties/dev.groovy'

                    // Use ConfigSlurper to parse the properties file
                    def configSlurper = new ConfigSlurper().parse(new File(propertiesFilePath).toURL())

                    // Access and print specific key-value pairs
                    echo "Value for Key 'username': ${configSlurper.Monday}"
                    echo "Value for Key 'password': ${configSlurper.Tuesday}"
                }
            }
        }
    }
}

    

