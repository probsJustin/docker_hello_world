pipeline {
  agent none
  stages {
    stage('Maven Install') {
      agent {
        docker {
          image 'ubuntu:16.04'
        }
      }
      steps {
        sh 'lsb_release'
      }
      steps {
        sh 'apt-get install -y docker.io '
      }
    }
    stage('Docker Build') {
      agent any
      steps {
        sh 'docker build -t test .'
      }
    }
  }
}