node {
    stage('Clone repository') {
        git credentialsId: 'docker-jenkins', url: 'https://github.com/shimyoonbum/fc-django.git'
    }

    stage('Build image') {
       dockerImage = docker.build("xxyt778/web_count:v1.0")
    }

    stage('Push image') {
        withDockerRegistry([ credentialsId: "jenkins-token", url: "" ]) {
        dockerImage.push()
        }
    }
}
