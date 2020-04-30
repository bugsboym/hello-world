pipeline {
  agent any
  stages {
    stage('start') {
      steps {
        sh 'hostname'
        echo 'hello'
      }
    }

    stage('post') {
      parallel {
        stage('post') {
          steps {
            sh 'who'
            robot 'test'
          }
        }

        stage('test1') {
          steps {
            sh 'echo "Hello Mark"'
          }
        }

      }
    }

  }
}