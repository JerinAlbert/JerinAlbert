pipeline {
  agent any
  stages {
    stage ('Initialize') {
      steps {
        sh '''
               echo "PATH = ${PATH}"
               echo "M2_HOME = ${M2_HOME}"
           '''
      }
    }
      stage('check for secerets') {
          steps {
              sh 'rm trufflehog || true'
              sh 'docker run gesellix/trufflehog https://github.com/JerinAlbert/JerinAlbert.git > trufflehog'
              sh 'cat trufflehog'
          }
      }
  }
}
