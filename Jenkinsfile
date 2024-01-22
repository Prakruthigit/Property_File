pipeline {
    agent any

    stages {

         stage('Checkout git') {
            steps {
                checkout scm
            }
        }
		
	stage('Gradle Build'){
            steps{
                sh "mvn clean package -DskipTests"
		sh "mv target/*.jar target/app_${BUILD_NUMBER}.jar"
            }
        }

	stage('Parallel Deploy'){
	      parallel {
		      stage('US'){
			    when {
				    expression {env.BRANCH_NAME == 'new-branch'}
			    }
			    steps{
				    echo "US"
			    }
		      }
		      stage('EU'){
			      when{
				   expression {env.BRANCH_NAME == 'new-branch'}   
			      }
			      steps{
				      echo "EU"
			      }
		      }
	      }
	}

    }    
}
