pipeline {
    agent {
        node {
            label 'centos8'
        }
    }
  stages {
    stage('Clone GIT repo') {
      steps {
        git credentialsId: '6478a9cf-dbae-41cc-8029-5a756048873a', url: 'https://github.com/ramanjk/sample-java-github-hook-test.git'
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
