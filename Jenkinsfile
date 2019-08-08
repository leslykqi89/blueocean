pipeline {
  agent any
  stages {
    stage('Lint HTML') {
      agent any
      steps {
        sh '''tidy -q -e *.html
'''
      }
    }
  }
}