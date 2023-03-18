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
          sh 'docker run --rm -v "$PWD:/pwd" trufflesecurity/trufflehog:latest github --org=trufflesecurity'
          //sh 'trufflehog3 git https://github.com/satishcloudsec/hello-world.git'
      }
     }
  }
}
