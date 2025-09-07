pipeline {
  agent {
    label 'docker'
  }
  stages {
    stage('Build docker image') {
      steps {
        sh 'docker build -t eslamnasser100/docker-react -f Dockerfile.dev .'
        }
    }
    stage('Run Tests') {
      steps {
        script {
          env.DOCKER_BUILDIT = 1
          sh 'docker run -e CI=true eslamnasser100/docker-react npm run test'
        }
      }
    }
  }
}
