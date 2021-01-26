pipeline {
  agent { label 'slave' }
  
    stages {
    stage('Source') {
      steps {
        git 'git@github.com:bobby4216/pom.git'
      }
    }


        stage ('Build') {
            steps {
                sh 'mvn -Dmaven.test.failure.ignore=true install' 
            }
            }
        }
    }
