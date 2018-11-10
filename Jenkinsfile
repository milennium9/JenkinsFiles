pipeline {
  agent any
  stages {
    stage('Windows') {
      steps {
        git(credentialsId: 'VSTSToken', url: 'https://milennium9.visualstudio.com/_git/DevilsBook', branch: 'home')
        build(job: 'DevilBook_18_BuildServer', propagate: true, wait: true)
      }
    }
  }
}