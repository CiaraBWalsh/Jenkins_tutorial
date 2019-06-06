pipeline {
  agent {
    docker {
      image 'python:3.5.1'
    }

  }
  stages {
    stage('Build') {
      steps {
        echo 'Building...'
        sh 'python --version'
        sh 'echo "Hello World"'
        sh '''echo "Multiline shell steps works too"
ls -lah'''
      }
    }
    stage('Test') {
      steps {
        echo 'Testing...'
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying..'
        timeout(time: 1, unit: 'MINUTES') {
          sh './health-check.sh'
        }

      }
    }
  }
}