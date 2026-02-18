pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
        sh 'echo Building backend...'
        sh 'mvn clean package -DskipTests'
      }
    }

    stage('Docker Build') {
      steps {
        sh 'docker build -t backend-app .'
      }
    }
  }
}
