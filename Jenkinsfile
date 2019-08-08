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
    stage('Upload to AWS') {
      steps {
        withAWS(credentials: 'MyCredentials', region: 'us-east-1') {
          s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, bucket: 'jenkins-ex3-udacity', file: 'index.html')
        }

      }
    }
  }
}