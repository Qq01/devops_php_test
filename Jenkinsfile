node {
    def app

    stage("Clone repository") {
        checkout scm
    }
    
    stage("Build image") {
        app = docker.build("qq01/docker-example")
    }

    stage("Test image") {
        app.inside {
            sh 'echo "Test passed"'
        }
    }
    
    stage("Push image") {
        docker.withRegistry("https://registry.hub.docker.com", "docker-hub-credentials") {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
}