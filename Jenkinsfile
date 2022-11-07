pipeline {
    agent any
    
    stages {
        stage('Test') {
            steps {
                git 'https://github.com/joyienjoy/java-helloworld.git'
                sh "mvn test"
            }
        }
        stage('Build') {
            steps {
                sh "mvn clean package"
            }
        }
        stage('Deploy') {
            steps {
              sshagent(['tomcat-centos']) {
                    sh '''
                    
                    scp ssh -o StrictHostKeyChecking=no target/*.war joydeep@52.246.168.32
                    
                    ssh joydeep@52.246.168.32: sudo systemctl start tomcat
                    '''
            }
        }
      }
    }
}
