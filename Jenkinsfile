pipeline {
  agent any
  stages {
    stage('test ') {
      parallel {
        stage('Test ') {
          steps {
            sh 'touch bonjour'
            echo 'hello phrase de test '
            sh ' mvn clean test'
          }
        }

        stage('built') {
          environment {
            JAVA_HOME = '/usr/lib/jvm/java-8-openjdk-amd64/'
          }
          steps {
            sh 'git clone https://github.com/kliakos/sparkjava-war-example.git'
            sh 'cd sparkjava-war-example'
            sh 'mvn clean install '
            archiveArtifacts 'target/*.war'
          }
        }

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