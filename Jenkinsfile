pipeline {
  agent any
  stages {
    stage("stage 1") {
      steps {
        echo "Current build number: ${BUILD_NUMBER}"
      }
    }
    stage("stage 2") {
      steps {
        script {
          env.RANDOM_NUMBER = powershell('Get-Random')
        }
        sh 'echo $RANDOM_NUMBER'
      }
    }
    stage("stage 3") {
      steps {
        echo 'stage 3'
      }
    }
    stage("stage 4") {
      steps {
        echo "Random generated number from stage 2: "
      }
    }
  }
}
