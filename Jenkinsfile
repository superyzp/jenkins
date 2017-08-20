pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        parallel(
          "build": {
            echo 'building'
            
          },
          "node": {
            node(label: 'dev') {
              sh '''sshagent (credentials: ["ikcrm_dev"]) {
  sh 'ssh -o StrictHostKeyChecking=no -l ikcrm_dev dev.ikcrm.com uname -a'
}'''
              }
              
              
            }
          )
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
          sh 'ssh'
        }
      }
    }
  }