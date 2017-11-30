pipeline {
  agent none
  stages {
    stage('Testing') {
      agent {
        docker {
            image 'golang'
        }
      }
      steps {
        sh 'go test'
      }
    }
    stage('Deploy') {
        agent none
        steps {
            script {
                def customImage = docker.build("headead/jks_maths:${env.BUILD_NUMBER}")
            }
        }
    }
  }
}