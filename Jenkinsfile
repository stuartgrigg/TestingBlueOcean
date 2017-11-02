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
        sh '''echo "qwertyuiop"
echo $BRANCH_NAME'''
        sh 'git status'
      }
    }
    stage('Gitty thing') {
      steps {
        sh '''CURRENT_REVISION="$(git rev-parse HEAD)"
MASTER_REVISION="$(git rev-parse refs/remotes/origin/master/HEAD)"
git merge-base $CURRENT_REVISION $MASTER_REVISION'''
      }
    }
  }
}