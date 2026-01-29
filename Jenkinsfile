pipeline {
  agent any

  stages {
    stage('Clone') {
      steps {
        git 'git@github.com:Madhanraj30/jenkins-demo.git'
      }
    }

    stage('Build Docker Image') {
      steps {
        sh 'docker build -t jenkins-demo-app .'
      }
    }

    stage('Deploy Container') {
      steps {
        sh '''
        docker rm -f jenkins-app || true
        docker run -d -p 80:80 --name jenkins-app jenkins-demo-app
        '''
      }
    }
  }
}
