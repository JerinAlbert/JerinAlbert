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
      stage ('SCA') {
          steps{
              sh 'rm owasp || true'
              sh 'wget "https://raw.githubusercontent.com/JerinAlbert/JerinAlbert/main/owasp-dependency-check.sh" '
              sh 'chmod +x owasp-dependency-check.sh'
              sh 'bash owasp-dependency-check.ch'
          }
      }
  }
}
