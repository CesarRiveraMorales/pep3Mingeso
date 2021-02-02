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
        sh 'npm install'
        sh 'npm install -g http-server'
      }
    }

    stage('Test') {
      steps {
        sh 'npm run test -- --coverage --watchAll=false'
      }
    }

    stage('Linter') {
      steps {
        sh 'npm run lint'
      }
    }

    stage('Build/Deploy'){
      steps {
        sh 'npm run build'
        sh 'npm run http-server ./dist -p 3454'
      }
    }
  }
  environment {
    CI = 'true'
  }
}