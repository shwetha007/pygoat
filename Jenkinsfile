pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
        echo 'Building...'
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
 	  targetFile: 'requirements.txt',
	additionalArguments: '--package-manager=pip --command=python3 -- --allow-missing'
	  
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