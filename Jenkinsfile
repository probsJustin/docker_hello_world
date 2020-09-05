pipeline {
    agent {
        docker { image 'ubuntu:16.04' }
    }
    stages {
        stage('example_1') {
            steps {
                sh 'apt-get update -y && \
    apt-get install -y python-pip python-dev',
                sh 'python /app/app.py'
            }
        }
    }
}