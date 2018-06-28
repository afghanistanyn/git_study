pipeline {
  agent any
  stages {
    stage('env check') {
      steps {
        isUnix()
        sh 'java -version'
        sh 'mvn -version'

       input message: 'input branch name for this job', ok: 'ok', parameters: [string(defaultValue: 'test', description: 'branch name', name: 'branch'), string(defaultValue: '', description: 'commit to switch', name: 'commit')]

	sh "echo ${env.branch}"
	sh "echo ${env.commit}"

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
        sh 'echo "mail to developers"'
      }
    }
  }
}
