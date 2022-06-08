pipeline {
  agent any
  stages {
    stage('Test ') {
      steps {
        sh 'touch bonjour'
        echo 'hello phrase de test '
        sh ' mvn clean test'
      }
    }

    stage('reports') {
      steps {
        junit 'target/surefire-reports/*.xml'
      }
    }

    stage('end') {
      steps {
        sh 'echo "fin des tâches, ça c\'est bien passé" '
      }
    }

  }
}