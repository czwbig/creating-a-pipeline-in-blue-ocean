pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''npm install --registry=https://registry.npm.taobao.org
'''
      }
    }

    stage('Run') {
      steps {
        sh 'npm start'
      }
    }

  }
}