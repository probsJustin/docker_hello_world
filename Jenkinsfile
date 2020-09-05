pipeline {
  agent none
  stages {
    stage('Ubuntu Install') {
      agent {
        docker {
          image 'ubuntu:16.04'
        }
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