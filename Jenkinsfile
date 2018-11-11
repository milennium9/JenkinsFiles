pipeline {
    agent none
    stages {
        stage('BuildStart') {
            parallel {
                stage('Server') {
                    agent {
                        label 'master'
                    }
                    steps {
                        build job: 'DevilBook_18_BuildServer', propagate: true, wait:true
                    }
                }
                stage('Windows Bundle') {
                    agent {
                        label 'master'
                    }
                    steps {
                        build job: 'DevilBook_18_Bundle_Windows', propagate: true, wait:true
                    }
                }
                stage('Android Bundle') {
                    agent {
                        label 'slave1'
                    }
                    steps {
                        build job: 'DevilBook_18_Bundle_Android', propagate: true, wait:true
                    }
                }
				//*
                stage('iOS Bundle') {
                    agent {
                        label 'slave2'
                    }
                    steps {
                        build job: 'DevilBook_18_Bundle_iOS', propagate: true, wait:true

                    }
                }
				//*/
            }
        }
    }
}
