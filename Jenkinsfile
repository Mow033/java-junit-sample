pipeline {
  agent any
  stages {
    stage('Test ') {
      steps {
        echo 'Hello '
        dir(path: 'java-junit-sample_master/')
        sh ' mvn clean test'
        junit 'target/surefire-reports/*.xml'
        cleanWs()
      }
    }

    stage('build') {
      steps {
        git(url: 'https://github.com/kliakos/sparkjava-war-example.git', branch: 'master')
        sh 'mvn clean install '
      }
    }

    stage('end') {
      steps {
        sh 'echo "fin des tâches, ça c\'est bien passé" '
      }
    }

  }
}