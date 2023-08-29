pipeline {
    agent any 
	environment {
		def scannerHome = tool 'Sonar-scanner';
		
	
		
	}
    stages {
	  stage('SCM') {
		  steps {
		    checkout scm
		  }
	  }
	    
	
	    
	    
	    


	  

	  stage('SAST Analysis-SonarQube') {
		  steps {
		    withSonarQubeEnv('Sonarqube') {
		      sh "${scannerHome}/bin/sonar-scanner"
	    }
	    }
	  }


    
	    
	  stage ("Dynamic Analysis - OWASP ZAP") {
		  steps {
		  	sh "docker run -t owasp/zap2docker-stable zap-baseline.py -t http://35.222.234.180/ || true"
		 	 }
			}
	    

	    

	    

	
	
	

	
    

        

    }
}
