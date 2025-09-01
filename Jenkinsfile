pipeline {
    agent { label 'linux-node' } 
    stage('Build Docker Image') {
        steps {
            script {
                docker.build("node-webapp-image") 
            }
        }
    }
    stage('Run Docker Container') {
        steps {
            script {
                docker.image("node-webapp-image").run
            }
        }
    }
}

