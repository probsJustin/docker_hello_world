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
        sh 'lsb_release'
      }
    }
    stage('git pull') {
      agent any
      steps {
        sh 'git clone https://github.com/probsJustin/docker_hello_world.git'
      }
    }
  }
}