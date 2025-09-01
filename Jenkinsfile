pipeline {
    agent { label 'linux-node' } 
    options {
        skipDefaultCheckout() 
    }

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/pbernal-opswerks/node-webapp.git' 
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

