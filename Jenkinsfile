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

    stage('reports') {
      parallel {
        stage('reports') {
          steps {
            robot(outputPath: '/test/', logFileName: 'test.xml', outputFileName: 'test.xml', passThreshold: 1, reportFileName: 'test.xml', unstableThreshold: 1)
          }
        }

        stage('error') {
          steps {
            withSonarQubeEnv 'sonar_local'
          }
        }

      }
    }

  }
}