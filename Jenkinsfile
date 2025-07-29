pipeline {
  agent any
  stages {
    stage('Create Env') {
      steps {
        nodejs('node-latest') {
          sh '''npm i -g @angular/cli


'''
        }

      }
    }

    stage('Install Dependencies') {
      steps {
        nodejs('node-latest') {
          sh 'npm i'
        }

      }
    }

  }
}