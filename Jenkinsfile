pipeline {
    agent { label 'linux-node' } 
    options {
        skipDefaultCheckout() 
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', 
                    credentialsId: '14d1c33d-40b6-428f-9ab4-851bff4e024c', 
                    url: 'https://github.com/pbernal-opswerks/node-webapp.git' 
            }
        }
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
                    docker.image("node-webapp-image").run("-p 3000:3000") 
                }
            }
        }
    }
}

