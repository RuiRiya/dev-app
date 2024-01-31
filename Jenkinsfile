pipeline {
  agent any
  stages {
    stage('dev') {
      steps {
        sh '''pwd
ls
whoami'''
      }
    }

    stage('test') {
      parallel {
        stage('test') {
          steps {
            echo 'this is testing'
            sh 'touch abc'
          }
        }

        stage('test2') {
          steps {
            sleep 5
            echo '2nd test'
          }
        }

      }
    }

    stage('prod') {
      steps {
        echo 'final deployment'
        fileExists 'abc'
      }
    }

  }
}