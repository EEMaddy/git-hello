pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        nodejs('node-latest') {
          sh 'ng build'
        }

      }
    }

  }
}