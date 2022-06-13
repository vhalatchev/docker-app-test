pipeline {
    options {
        timeout(time: 1, unit: 'HOURS')
    }

    agent { dockerfile true }
        // 'ubuntu-1804 && amd64 && docker'
    
    stages {
<<<<<<< HEAD
      stage('Authenticate'){
            steps {
               withDockerRegistry([url: 'https://registry.hub.docker.com', credentialsId:'dockerHubCred']){
		sh 'docker login -u vihroman'
                  }
        	}	        
	       }

=======
      /* stage('Authenticate'){
            steps {
               {withDockerRegistry([url: 'https://registry.hub.docker.com', credentialsId:'dockerHubCred'])}
                  }
        }*/
        
>>>>>>> 91ca696b76970be5733bf199b6ca4794ead44f60
        stage('Build') {
            steps {
            sh 'docker build -t getting-started .'
            sh 'docker run -dp 3000:3000 getting-started'
            }
        }

        stage('Push'){
            steps { 
<<<<<<< HEAD

=======
                 withDockerRegistry([url:'https://registry.hub.docker.com', credentialsId: 'dockerHubCred']){
>>>>>>> 91ca696b76970be5733bf199b6ca4794ead44f60
                    sh ('docker image tag getting-started:latest vihroman/dockerpush:newpushtest3')
                    sh ('docker image push vihroman/dockerpush:newpushtest3')
                   }
                }
            }
        }

