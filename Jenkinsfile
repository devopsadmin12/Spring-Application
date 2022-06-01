pipeline { 
  agent any
  tools {
    maven 'Maven'
  }
  stages {
    stage ('SCM Checkout') {
      steps {
      git 'https://github.com/devopsadmin12/Spring-Application.git'
      }
    }
  stage ('SAST') {
      steps {
        withSonarQubeEnv('SonarQube') {
          sh 'mvn sonar:sonar'
          sh 'cat target/sonar/report-task.txt'
        }
      }
    }
  
  }
}
