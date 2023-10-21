pipeline {
    agent any
    
    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    def customImage = docker.build("akashhulke/HelloWorld:${env.BUILD_ID}")
                }
            }
        }
        stage('Push Docker Image to Docker Hub') {
            steps {
                script {
                    customImage.push()
                }
            }
        }
    }
}
