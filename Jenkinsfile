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
        sh './jenkins/scripts/deliver.sh'
        input(message: 'Finished using the web site? (Click "Proceed" to continue)', id: 'finished?', ok: './jenkins/scripts/kill.sh')
        sh './jenkins/scripts/kill.sh'
      }
    }

  }
}