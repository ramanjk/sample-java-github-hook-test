pipeline {
  agent {
    docker {
      image 'centos:latest'
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
    
    stage('Deploy') {
      steps {
        sh 'echo "Deploying the software on Kubernetes"'
      }
    }
  }
}
