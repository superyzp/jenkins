pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'building'
      }
    }
    stage('test') {
      steps {
        echo 'testing'
      }
    }
    stage('deploy') {
      steps {
        echo 'deploying'
        sh '''sshagent (credentials: ['ikcrm_dev']) {
    sh 'ssh -o StrictHostKeyChecking=no -l ikcrm_dev dev.ikcrm.com uname -a'
  }'''
        }
      }
    }
  }