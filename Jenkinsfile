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
    }
    stage('Docker Build') {
      agent any
      steps {
        sh 'docker build -t test .'
      }
    }
  }
}