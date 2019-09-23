pipeline {
  agent { docker { image 'python:3.7.2' } }
  stages {
    stage('test') {
      withPythonEnv('python') {
        sh 'pip3 install --user -r requirements.txt'
      }
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
