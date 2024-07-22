pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      agent any
      steps {
        sh '''echo "I am a ${BUZZ_NAME}"
./hello.sh'''
        archiveArtifacts(artifacts: 'target/*.jar', fingerprint: true)
      }
    }

    stage('Buzz Test') {
      parallel {
        stage('Buzz Test') {
          steps {
            sh './test_hello.sh'
            junit '**/surefire-reports/**/*.xml'
          }
        }

        stage('Testing B') {
          steps {
            sh '''sleep 10
echo done'''
          }
        }

      }
    }

  }
  environment {
    BUZZ_NAME = 'Worker Bee'
  }
}