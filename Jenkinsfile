pipeline {
    options {
        timeout(time: 1, unit: 'HOURS')
    }
    agent {
        label 'ubuntu-1804 && amd64 && docker'
    }
    stages {
        stage('build and push') {
            when {
                branch 'master'
            }
            sh "docker build -t vihroman/getting-started ."

            steps {
                withDockerRegistry([url: "registry.hub.docker.com", credentialsId: "dockerHubCred"]) {
                    sh("docker push vihroman/getting-started")
                }
            }
        }
    }
}
