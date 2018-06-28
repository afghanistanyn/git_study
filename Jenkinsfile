pipeline {
  agent any
  stages {
    stage('Env Check') {
      steps {
        isUnix()
        sh 'java -version'
        sh 'mvn -version'
        pwd()
        waitUntil() {
          input(message: 'are you ready', ok: 'go')
        }

      }
    }
    stage('build') {
      steps {
        sh 'echo "build"'
      }
    }
    stage('deploy') {
      steps {
        sh 'echo "package & deploy"'
      }
    }
    stage('report') {
      steps {
        sh 'echo "mail to dev"'
      }
    }
  }
}