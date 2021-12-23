pipeline {
  agent any
  parameters {
    string(name: 'randomNumber', defaultValue: '', description: 'random generated number')
  }
  stages {
    stage("stage 1") {
      steps {
        echo "Current build number: ${BUILD_NUMBER}"
      }
    }
    stage("stage 2") {
      steps {
        script {
          env.Number = ''  
          powershell('$env:Number = Get-Random')
          echo "${env.Number}"
        } 
      }
    }
    stage("stage 3") {
      steps {
        echo 'stage 3'
      }
    }
    stage("stage 4") {
      steps {
        echo "Random generated number from stage 2: ${params.randomNumber}"
      }
    }
  }
}
