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
                docker.withRgistry ('https://registry.hub.docker.com', 'dockerhub')
                dockerapp.Push('latest')
                dockerapp.Push("${env.BUILD_ID}")
            }
        }
    }
    }

}

