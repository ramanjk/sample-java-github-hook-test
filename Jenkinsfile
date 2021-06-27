pipeline {
  agent {
    node {
      label 'centos8'
    }

  }
  stages {
    stage('Clone GIT repo') {
      steps {
        sh 'echo cloning git repository'
      }
    }

    stage('Build') {
      steps {
        sh 'echo "Building the code"'
      }
    }

  }
}