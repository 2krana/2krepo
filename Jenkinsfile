pipeline {
  agent any
  stages {
    stage('Stage 1') {
      steps {
        parallel(
          "Node 1": {
            echo 'Step 1'
            echo 'Step 2'
            
          },
          "Node 2": {
            echo 'Step 3'
            
          }
        )
      }
    }
  }
}