pipeline {
    agent {
        node {
            label 'centos8'
        }
    }
  stages {
    stage('Clone GIT repo') {
      steps {
        git credentialsId: 'caa166af-b9d9-4ffc-bf52-c54744f4fbbb', url: 'https://github.com/ramanjk/sample-java-github-hook-test.git'
      }
    }
    stage('Gradle Build') {
        steps {
            sh './gradlew build'
        }
    }
    stage('Docker image Build') {
        steps {
            sh "sudo docker build -t rathinamtrainers/myjavaapp:${env.BUILD_ID} ."
            sh "sudo docker tag rathinamtrainers/myjavaapp:${env.BUILD_ID} rathinamtrainers/myjavaapp:latest"
        }
    }
  }
}
