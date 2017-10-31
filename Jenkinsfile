pipeline {
    agent any
    stages {
        stage('build and test apps') {
            steps {
                parallel(
                    "app1": {
                        sh 'docker build -t app_1 app_1'
                        sh 'docker run app_1'
                    },
                    "app2": {
                        sh 'docker build -t app_2 app_2'
                        sh 'docker run app_2'
                    }
                )
            }
        }
    }
}
