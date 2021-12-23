pipeline {
  agent any
  environment {
    RANDOM_NUMBER = 1
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
          RANDOM_NUMBER = powershell(returnStdout: true, script: 'Get-Random').trim()
        }
      }
    }
    stage("stage 3") {
      steps {
        script {
          showFreeSpace() 
        }
      }
    }
    stage("stage 4") {
      steps {
        echo "Random generated number from stage 2: ${RANDOM_NUMBER}"
      }
    }
  }
}

def showFreeSpace() {
  powershell '''
    $FreeDiskSpace = (Get-PSDrive -Name C | Select-Object -ExpandProperty free)/1073741824
    $FreeDiskSpaceRounded = [math]::Round($FreeDiskSpace,2)
    echo "Free space left (GB): $FreeDiskSpaceRounded"
    Get-Location
  '''
  echo "${WORKSPACE}"
}
