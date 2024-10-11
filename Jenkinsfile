pipeline {
  agent any
  tools {
      maven 'Maven 3.9.9'
    }
  stages {
    stage('Run the tests') {
      steps {
        script {
          mvn= tool (name: 'Maven 3.9.9', type: 'maven') + '/bin/mvn'
        }
        sh "${mvn} clean install"
      }
    }
  }
  post {
    always {
      junit 'target/surefire-reports/*.xml'
    }
  }
}
