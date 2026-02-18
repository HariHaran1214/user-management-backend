pipeline {
  agent any

  stages {

    stage('Debug') {
      steps {
        sh '''
        echo "=== WORKSPACE CONTENT ==="
        ls -la
        echo "=== POM SEARCH ==="
        find . -name pom.xml
        '''
      }
    }

    stage('Build with Maven') {
      steps {
        sh '''
        docker run --rm \
          -v $PWD:/app \
          -w /app \
          maven:3.9.6-eclipse-temurin-17 \
          sh -c "ls -la && mvn clean package -DskipTests"
        '''
      }
    }

    stage('Docker Build') {
      steps {
        sh 'docker build -t user-management-backend .'
      }
    }

  }
}
