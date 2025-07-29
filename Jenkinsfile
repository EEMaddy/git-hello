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

    stage('Build') {
      agent {
        node {
          label 'node-slave'
        }

      }
      steps {
        nodejs('node-latest') {
          sh 'ng build'
        }

      }
    }

    stage('Deployment') {
      steps {
        sh 'rsync -avz /dist/angular-hello root@probatusai.com:/tmp'
      }
    }

  }
}