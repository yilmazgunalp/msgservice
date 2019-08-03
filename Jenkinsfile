pipeline {
  agent none
  triggers { upstream(upstreamProjects: '../wss/master', threshold: hudson.model.Result.SUCCESS)}
  stages {
    stage('Build') {
  agent {
    docker {
      image 'node:10'
      args '-p 3000:3000 -u 0'
    }
  }
      steps {
        sh 'npm install'
        sh 'echo hello world'
        sh 'echo hello Jenkins'
      }
    }
}
  environment {
    HOME = '.'
  }
}
