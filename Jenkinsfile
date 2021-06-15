pipeline {
    agent any
    stages {
        stage('Fetching and building the docker app') {
            steps {
                sh 'git clone https://github.com/anantjakhmola/testing-sample-1.git'
                sh '''
                    mvn clean package
                '''
            }
        }
        stage('checkout SCM and pushing docker'){
            steps {
                docker.withRegistry('https://registry.hub.docker.com', 'dockerhub-cred') {

                    def customImage = docker.build("anantj1/spring_pro:latest ")

                    /* Push the container to the custom Registry */
                    customImage.push()
                }
            }
        }
    }
}
