pipeline {
  agent any

  stages {

    stage('Install') {
      steps {
        sh 'npm install'
      }
    }

    stage('Test') {
      steps {
        sh 'npm test'
      }
    }

    stage('Build Docker') {
      steps {
        sh 'docker build -t local-cicd-app .'
      }
    }

    stage('Deploy') {
      steps {
        sh '''
          docker stop app || true
          docker rm app || true
          docker run -d -p 3000:3000 --name app local-cicd-app
        '''
      }
    }
  }
}
