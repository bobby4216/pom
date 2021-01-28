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
                withSonarQubeEnv('My SonarQube Server') {
                    // Optionally use a Maven environment you've configured already
                    withMaven(maven:'Maven 3.6.3') {
                        sh 'mvn clean package sonar:sonar'
                    }
                }
            }
        }
        stage ('Build') {
            steps {
                sh 'mvn -Dmaven.test.failure.ignore=true clean install' 
            }
            }
        }
    }
