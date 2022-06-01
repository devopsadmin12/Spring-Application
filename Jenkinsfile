pipeline { 
  agent any
  tools {
    maven 'Maven'
  }
  stages {
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
