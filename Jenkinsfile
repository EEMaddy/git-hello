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
      steps {
        nodejs('node-latest') {
          sh 'ng build'
        }

        stash(name: 'build-files', includes: 'dist')
      }
    }

    stage('Deployment') {
      agent {
        node {
          label 'node-slave'
        }

      }
      steps {
        unstash 'build-files'
        sh 'rsync -avz dist root@cc.probatusai.com:/tmp'
      }
    }

  }
}