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
          docker.withRegistry('https://github.com/rggaikwad/Website-PRT-ORG.git', 'DOCKERHUB_CREDENTIALS') {
            docker.image('rggaikwad17/website-prt-org').push('latest')
          }
        }
      }
    }
