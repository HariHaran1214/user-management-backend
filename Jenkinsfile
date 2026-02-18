pipeline {
  agent any

  stages {

    stage('Build with Maven') {
      steps {
        sh '''
        docker run --rm \
          -v $PWD:/app \
          -w /app \
          maven:3.9.6-eclipse-temurin-17 \
          mvn clean package -DskipTests
        '''
      }
    }

    stage('Docker Build') {
      steps {
        sh '''
        docker build -t user-management-backend .
        '''
      }
    }

  }
}
