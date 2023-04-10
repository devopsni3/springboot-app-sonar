pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage('SonarQube analysis') {
      steps {
        withSonarQubeEnv('sonar') {
          mvn verify org.sonarsource.scanner.maven:sonar-maven-plugin:sonar -Dsonar.projectKey=test-project11
        }
      }
    }
  }
}
