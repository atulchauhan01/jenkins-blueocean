pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        validateDeclarativePipeline '/'
      }
    }

    stage('pull image') {
      steps {
        echo 'pull image'
      }
    }

    stage('update tag') {
      steps {
        warnError(catchInterruptions: true, message: 'catch error') {
          echo 'error occured'
        }

      }
    }

    stage('push image') {
      steps {
        echo 'push image'
      }
    }

    stage('deployment') {
      parallel {
        stage('deployment') {
          steps {
            echo 'deployment'
          }
        }

        stage('data migration') {
          steps {
            echo 'data migration'
          }
        }

      }
    }

  }
  environment {
    branch = 'dev'
  }
}