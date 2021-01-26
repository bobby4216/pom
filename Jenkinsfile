pipeline {
  agent { label 'slave' }
  stages {
    stage('Source') {
      steps {
        git 'git@github.com:bobby4216/pom.git'
      }
    }
    stage('Compile') {
      tools {
        gradle 'mvn'
      }
      steps {
        sh 'mvn clean package'
      }
    }
  }
}
