pipeline {
    agent any

    stages {

        stage ("Build Docker Image") {
            steps {
                script {
                    dockerapp = docker.build("ABCS89/kubenews:${env.BUILD_ID}", '-f ./src/Dockerfile ./src')
                }
            }
        }

    }

}

