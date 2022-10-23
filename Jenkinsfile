pipeline {
    agent any

    stages {

        stage ("Build Docker Image") {
            steps {
                script {
                    dockerapp = docker.build("abcs89/kubenews:${env.BUILD_ID}", '-f ./src/Dockerfile ./src')
                }
            }
        }
    stage ('Push Docker Image') {
        steps {
            script {
                docker.withRgistry ('https://registry.hub.docker.com', 'jenkins')
                    dockerapp.push('latest')
                    dockerapp.push("${env.BUILD_ID}")
            }
        }
    }
    }

}

