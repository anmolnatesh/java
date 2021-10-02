pipeline {
  agent any
  tools {
    maven 'm3'
  }
  stages {
    stage('git') {
      steps{
        checkout scm
          }
    }
    stage('build') {
      steps{
        sh '''
        mvn clean package
        '''
      }
    }
    stage('docker')
    {
      agent {docker {image 'docker:latest'}}
      steps{
        sh "docker --version"
      }
    }
  }
}
