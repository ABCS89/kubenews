pipeline {
    agent any

    stages {

        stage ("Build Docker Image") {
            steps {
                script {
                    dockerapp = docker.build("abcs89/kubenews:${env.BUILD_ID}", '-f .Dockerfile ./src')
                }
            }
        }

    }

}

