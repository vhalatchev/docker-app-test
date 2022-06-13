pipeline {
    options {
        timeout(time: 1, unit: 'HOURS')
    }

    agent { dockerfile true }
    
   
    stages {
       stage('Authenticate'){
  	// agent { label 'ubuntu-1804 && amd64 && docker'}
	  steps{
               withDockerRegistry([url: 'https://registry.hub.docker.com', credentialsId:'dockerHubCred']){
		
                  }
        	}	        
	     } 

        
        stage('Build') {
            steps {
            sh 'docker build -t getting-started .'
            sh 'docker run -dp 3000:3000 getting-started'
            }
        }

        stage('Push'){
            steps { 
                    sh ('docker image tag getting-started:latest vihroman/dockerpush:newpushtest3')
                    sh ('docker image push vihroman/dockerpush:newpushtest3')
                   }
                }
            }
        }

