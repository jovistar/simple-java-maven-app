pipeline {
  agent {
    docker {
      image 'openjdk:8-alpine'
      args '-p 8081:8080'
    }

  }
  stages {
    stage('Build') {
      agent {
        docker {
          image 'maven:3-alpine'
          args '-v /root/.m2:/root/.m2'
        }

      }
      steps {
        sh 'mvn -B -DskipTests clean package'
      }
    }
  }
}