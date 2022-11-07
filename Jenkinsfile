pipeline {
  agent any
  stages {
    stage('pkg-test') {
      steps {
        sh 'mvn test'
      }
     }
    stage('pkg-build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage(pkg-deploy) {
      steps {
        sh '''
        
        '''
      }
    }

  }
}
