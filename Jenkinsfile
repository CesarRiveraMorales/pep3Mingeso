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
        sh 'npm install http-server'
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

    stage('Build'){
      steps {
        sh 'npm run build'
      }
    }
    stage('Deploy'){
      steps {
        sh 'echo (Acá debería ir el despliegue de la WebApp en un cluster de kubernetes)'
      }
    }
  }
  environment {
    CI = 'true'
  }
}