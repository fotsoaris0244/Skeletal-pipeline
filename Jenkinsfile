pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      agent any
      steps {
        sh './hello.sh'
      }
    }

    stage('Buzz Test') {
      steps {
        sh './test_hello.sh'
      }
    }

  }
}