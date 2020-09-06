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
    stage('Remove Old Docker Builds') {
      agent any
      steps {
        sh '''docker rm $(docker stop $(docker ps -a -q --filter ancestor=test-application --format="{{.ID}}"))'''
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
  }
}