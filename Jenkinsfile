pipeline {
  agent any
  stages {
    stage('Stage 1') {
      steps {
        parallel(
          "KlocWorkScan": {
            echo 'Step 1'
            echo 'Step 2'
            
          },
          "Create Package": {
            echo 'Step 3'
            sh 'sleep 30'
            
          }
        )
      }
    }
    stage('Final Step') {
      steps {
        sh 'echo \'Final Step\''
      }
    }
  }
}