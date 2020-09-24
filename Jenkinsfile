pipeline {
  agent any
  stages {
    stage('Build') {
      agent {
        docker {
          image 'node:12-alpine'
          args '-p 3000:3000'
        }

      }
      steps {
        sh '''npm install --registry=https://registry.npm.taobao.org
'''
      }
    }

    stage('Run') {
      agent {
        docker {
          image 'node:12-alpine'
          args '-p 3000:3000'
        }

      }
      steps {
        sh 'npm start'
      }
    }

  }
}