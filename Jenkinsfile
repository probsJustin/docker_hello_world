pipeline {
  agent none
  stages {
    stage('Ubuntu Install') {
      agent {
        docker {
          image 'ubuntu:latest'
        }
      }
      steps {
        sh 'ls -la'
      }
    }
    stage ('Run Application') {
      agent any
      steps {
        sh 'docker build ./ -t testApplication'
      }
    }
  }
}