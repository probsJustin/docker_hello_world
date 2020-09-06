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
    stage ('Docker build application') {
      agent any
      steps {
        sh 'docker build ./ -t pythontestapp:test-application'
      }
    }
    stage ('Docker run application') {
      agent any
      steps {
        sh 'docker run -d -p 5000:5000 test-application'
      }
    }
    stage ('Docker Testing') {
      agent any
      steps {
        sh 'ping 127.0.0.1:5000'
      }
    }
  }
}