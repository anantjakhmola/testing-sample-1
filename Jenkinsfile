node {
    def app

    stage('Clone repository') {
        

        checkout scm
    }
    stage('Build the maven'){
        sh 'mvn clean package'
    }

    stage('Build image') {
  
       app = docker.build("anantj1/spring_pro")
    }

 

    stage('Push image') {
        
        docker.withRegistry('https://registry.hub.docker.com', 'Dockerhub-cred') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
}
