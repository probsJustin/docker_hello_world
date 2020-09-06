pipeline {
  agent none
  stages {
    stage('Ubuntu Install') {
      agent {
        docker {
          image 'ubuntu:16.04'
        }
      }
      steps {
        sh 'lsb_release'
      }
    }
    stage('git pull') {
      agent any
      steps {
        sh 'git clone https://github.com/probsJustin/docker_hello_world'
      }
    }
  }
}