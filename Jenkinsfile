pipeline {
  agent any
  stages {
    stage('Create Env') {
      steps {
        nodejs('node-latest') {
          sh '''npm i -g @angular/cli
npm i
ng build
'''
        }

      }
    }

  }
}