pipeline {
  agent any
  stages {
    stage('Build and Test Apps') {
      parallel {
        stage('app1') {
          steps {
            sh 'docker build -t app_1 app_1'
            sh 'docker run app_1'
          }
        }
        stage('app2') {
          steps {
            sh 'docker build -t app_2 app_2'
            sh 'docker run app_2'
          }
        }
      }
    }
    stage('Silly Stuff') {
      steps {
        sh 'echo "qwertyuiop"'
      }
    }
  }
}