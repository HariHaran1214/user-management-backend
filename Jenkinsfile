pipeline {
  agent any

  stages {
    stage('Debug Workspace') {
      steps {
        sh '''
        echo "=== LIST ROOT ==="
        ls -la

        echo "=== FIND POM ==="
        find . -name "pom.xml"
        '''
      }
    }
  }
}
