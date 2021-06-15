node {
    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', 'Dockerhub-cred') {

        def customImage = docker.build("anantj1/spring_pro:latest ")

        /* Push the container to the custom Registry */
        customImage.push()
    }
}
