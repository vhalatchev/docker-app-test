pipeline {
    options {
        timeout(time: 1, unit: 'HOURS')
    }
    agent {
        label 'ubuntu-1804 && amd64 && docker'
    }
    stages {
        stage('Build') {
            steps {
            sh "docker build -t docker/getting-started ."    
            }

            steps {
            sh "docker run -dp 3000:3000 getting-started"
            }
        }
        stage('Push'){
            steps { withDockerRegistry([url: "https://registry.hub.docker.com", credentialsId: "dockerHubCred"]) {
                    sh "docker image tag getting-started:latest vihroman/dockerpush:newpushtest"
                    sh "docker image push vihroman/dockerpush:newpushtest"
                
                }
            }
        }
    }
}
