pipeline {
  agent { label 'slave' }
  
    stages {
    stage('Source') {
      steps {
     checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'd4038521-1c38-4e1d-a67a-424dd7176033', url: 'git@github.com:bobby4216/pom.git']]])
    }
}
stage('build && SonarQube analysis') {
            steps {
                
                        sh 'mvn clean package sonar:sonar -Dsonar.host.url=http://54.209.29.89:9000 -Dsonar.login=59f85c2b9e65634b6d71776e1e5d6dc07ab18ee9 -Dsonar.projectKey=first'
                 
            }
        }
        stage ('Build') {
            steps {
                sh 'mvn -Dmaven.test.failure.ignore=true clean install' 
            }
            }
        }
    }
