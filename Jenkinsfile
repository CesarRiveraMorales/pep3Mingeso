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
        sh 'docker build -t paginaVue'
        sh 'docker run -it -p 3454:3454 pagina paginaVue'
      }
    }
  }
  environment {
    CI = 'true'
  }
}