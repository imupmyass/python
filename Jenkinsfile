pipeline {
  agent { docker { image 'jcdemo/flaskapp' } }
  stages {
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
