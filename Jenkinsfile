pipeline {
  agent { docker { image 'python:3.7.2' } }
  stages {
    stage('build') {
      steps {
        sh 'whoami'
        sh 'pip3 install --user -r requirements.txt'
      }
    }
    stage('test') {
      steps {
        sh 'python3 test.py'
      }
      post {
        always {
          junit 'test-reports/*.xml'
        }
      }    
    }
  }
}
