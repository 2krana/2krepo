pipeline {
  agent any
  stages {
    stage('Build_And_Run_Unit_tests') {
      steps {
        echo 'Running Build_And_Run_Unit_tests'
        sh 'sleep 10'
      }
    }
    stage('Run_Klocwork_Scan') {
      steps {
        parallel(
          "Run_Klocwork_Scan": {
            echo 'Running Run_Klocwork_Scan'
            sh 'sleep 10'
            
          },
          "Create_Package": {
            sh 'sleep 5'
            script {
              try{
                timeout(time: 2, unit: 'SECONDS') {
                  sleep 10
                  echo 'Child Completed'
                }
              }catch(e){
                echo 'Caught the Exception'
              }
            }
            
            
          }
        )
      }
    }
    stage('Final Stage') {
      steps {
        sh 'echo \'Condition Met\''
      }
    }
  }
}