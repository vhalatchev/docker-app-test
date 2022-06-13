pipeline {
    options {
        timeout(time: 1, unit: 'HOURS')
    }

    agent { dockerfile true }
        // 'ubuntu-1804 && amd64 && docker'
    
    stages {
        stage('Authenticate'){
            steps {
                withDockerRegistry([url: 'https://registry.hub.docker.com', credentialsId: 'dockerHubCred'])
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
                    // sh docker container commit <container_id?> getting-started:latest
                    sh 'docker image tag getting-started:latest vihroman/dockerpush:newpushtest'
                    sh 'docker image push vihroman/dockerpush:newpushtest'
                
                }
            }
        }
     }
