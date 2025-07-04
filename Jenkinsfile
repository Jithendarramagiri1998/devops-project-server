pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/yourname/student-portal'
      }
    }
    stage('Build & Dockerize') {
      steps {
        sh 'docker build -t student-api ./backend'
        sh 'docker build -t student-ui ./student-portal'
      }
    }
    stage('Deploy') {
      steps {
        sh 'docker run -d -p 5000:5000 student-api'
        sh 'docker run -d -p 3000:3000 student-ui'
      }
    }
  }
}
