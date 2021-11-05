pipeline {
  agent any

  stages {
    stage('Git Clone') {
            steps{
        git url: 'https://github.com/buildpacks/sample-java-app.git'
            } 
    }
    stage('Test') {
	tools {
        snyk 'mySnyk'
      }	
      steps {
        echo 'Testing...'
        snykSecurity(
          snykInstallation: 'mySnyk',
          snykTokenId: 'mySnkToken',
          // place other parameters here
 	  //targetFile: 'Dockerfile',
	//additionalArguments: '--package-manager=pip --command=python3 -- --allow-missing'
	  
        )
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying...'
      }
    }
  }
}
