pipeline {
  agent any
  environment {
    DOCKERHUB_CREDENTIALS = credentials('dockerhub-credentials')
  }
  stages {
    stage('Build Docker Image') {
      steps {
        script {
          docker.build('rggaikwad17/website-prt-org')
        }
      }
    }
    stage('Push Docker Image') {
      steps {
        script {
          docker.withRegistry('https://registry.hub.docker.com', 'DOCKERHUB_CREDENTIALS') {
            docker.image('rggaikwad17/website-prt-org').push('latest')
          }
        }
      }
    }
    
}
