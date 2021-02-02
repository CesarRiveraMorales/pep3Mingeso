pipeline {
  agent {
    docker {
      image 'node:12'
      args '-p 3000:3000'
    }
  }
  stages {
    stage('Install packages') {
      steps {
        sh 'npm -g install'
        sh 'npm install -g @vue/cli'
      }
    }

    stage('Test') {
      steps {
        sh 'npm run test -- --coverage --watchAll=false'
      }
    }

    stage('Build/Deploy'){
      steps {
        sh 'npm run build'
      }
    }
  }
  environment {
    CI = 'true'
  }
}