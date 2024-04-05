pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh "mvn clean install"
            }
        }
        
        stage("build & SonarQube analysis") {
            agent any
            steps {
              withSonarQubeEnv('sonarqube') {
                sh 'mvn sonar:sonar'
              }
            }
          }
    }
}
