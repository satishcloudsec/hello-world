pipeline {
  agent any 
  tools {
    maven 'Maven'
  }
  stages {
    stage ('Initialize') {
      steps {
        sh '''
                    echo "PATH = ${PATH}"
            ''' 
      }
    }

    
     stage ('Build') {
      steps {
          sh 'pwd'
          sh 'mvn clean package'
      }
     }
    
         stage ('trufflehog scanning') {
      steps {
          sh 'pwd'
          sh 'echo $PATH'
          sh 'trufflehog3 git https://github.com/satishcloudsec/hello-world.git'
      }
     }
  }
}
