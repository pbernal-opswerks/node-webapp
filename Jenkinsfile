pipeline {
   agent { label 'linux-node'}
   stages {
    stage('Checkout') {
      steps {
        script {
           // The below will clone your repo and will be checked out to master branch by default.
           git 'https://github.com/pbernal-opswerks/node-webapp.git'
           // Do a ls -lart to view all the files are cloned. It will be clonned. This is just for you to be sure about it.
           sh "ls -lart ./*" 
           // List all branches in your repo. 
           sh "git branch -a"
           // Checkout to a specific branch in your repo.
           sh "git checkout main"
          }
       }
    }
    stage('Docker Build') {
    agent { dockerfile true }
      steps {
        sh 'docker build -t jenkins/image:latest .'
        sh 'docker images'
        sh 'docker run '
      }
  }
}
}
