pipeline {
    agent any
    stages {
       stage('unit tests') {
          steps {
            sh 'ant -f test.xml -v'
            junit 'reports/restul.xml'
          }
       }
      stage('build') {
       steps {
         sh 'ant -f build.xml -v'
            }
          }
        }
     post {
       always {
        archiveArtifacts artifacts: 'dist/*.jar', fingerprint: true
       }
    }
  }
