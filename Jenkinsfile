pipeline {
    agent {
        node {
            label 'centos8'
        }
    }
  stages {
    stage('Clone GIT repo') {
      steps {
        git credentialsId: 'c74c6485-9f3a-4da9-bc52-354dc2d5320d', url: 'https://github.com/rajanirugur/sample-java-project-demo1.git'
      }
    }
    stage('Gradle Build') {
        steps {
            sh './gradlew build'
        }
    }
    stage('Docker image Build') {
        steps {
            sh "docker build -t rathinamtrainers/myjavaapp:${env.BUILD_ID} ."
            sh "docker tag rathinamtrainers/myjavaapp:${env.BUILD_ID} rathinamtrainers/myjavaapp:latest"
        }
    }
  }
}
