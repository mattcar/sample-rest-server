pipeline {
   agent { docker { image 'maven:3.5-alpine' } }

   options {
      buildDiscarder(logRotator(numToKeepStr:'10'))
   }

   stages {
      stage('Build') {
         steps {
            sh 'mvn clean package'
         }
      }
   }
}
  agent {
    docker {
      image 'maven:3.5-alpine'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage('Develop Tests') {
      when {
        beforeAgent true
        branch 'develop'
      }
      steps {
        echo 'Run the develop tests!'
      }
    }
  }
  options {
    buildDiscarder(logRotator(numToKeepStr: '10'))
  }
}
