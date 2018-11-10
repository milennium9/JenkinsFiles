pipeline {
  agent any
  stages {
    stage('Windows') {
      agent {
        node {
          label 'master'
        }

      }
      steps {
        build(job: 'DevilBook_18_BuildServer', propagate: true, wait: true)
      }
    }
  }
}