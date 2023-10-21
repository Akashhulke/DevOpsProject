pipeline {
    agent any
    
    stages {
        stage('Build Docker Image') {
            steps {
                script {

		    def javacPath = '/usr/lib/jvm/java-11-openjdk-amd64/bin/javac'

		    sh "${javacPath} HelloWorld.java"

                    def customImage = docker.build("akashhulke/helloworld:${env.BUILD_ID}")
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
