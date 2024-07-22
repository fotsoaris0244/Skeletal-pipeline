pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      agent any
      steps {
        sh './hello.sh'
        archiveArtifacts(artifacts: 'target/*.jar', fingerprint: true)
      }
    }

    stage('Buzz Test') {
      steps {
        sh './test_hello.sh'
      }
    }

  }
}