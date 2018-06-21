pipeline {
  agent {
    node {
      label 'leonj'
    }

  }
  stages {
    stage('install') {
      steps {
        sh 'npm install'
      }
    }
    stage('test1') {
      parallel {
        stage('test1') {
          steps {
            sh 'npm run test1'
          }
        }
        stage('test2') {
          steps {
            sh 'npm run test2'
          }
        }
        stage('test3') {
          steps {
            sh 'npm run test3'
          }
        }
      }
    }
    stage('build') {
      steps {
        sh 'docker build -t leonjalfon1/substraction-service-test:latest .'
      }
    }
    stage('push') {
      steps {
        sh '''docker login -u selaworkshops -p Sela1234!
docker push leonjalfon1/substraction-service-test:latest'''
      }
    }
  }
}