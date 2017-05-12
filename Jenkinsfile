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
            build 'VinJob2'
            
          },
          "Create_Package": {
            echo 'Running Create_Package'
            sh 'sleep 5'
            
          }
        )
      }
    }
    stage('Invoke_NexusIQ_Scan_on_Jenkins') {
      steps {
        parallel(
          "Invoke_NexusIQ_Scan_on_Jenkins": {
            echo 'Running Invoke_NexusIQ_Scan_on_Jenkins'
            sh 'sleep 5'
            
          },
          "Package deployment on Second QA Server for IA": {
            echo 'Running Package deployment on Second QA Server for Impact Analyzer'
            sh 'sleep 10'
            
          },
          "Package deployment on QA Server": {
            echo 'Running Package deployment on QA Server'
            sh 'sleep 10'
            
          }
        )
      }
    }
    stage('Run_Impact_Analyzer') {
      steps {
        parallel(
          "Run_Impact_Analyzer": {
            echo 'Running Run_Impact_Analyzer'
            sh 'sleep 10'
            
          },
          "Copy run config file for automation": {
            echo 'Running Copy run config file for automation'
            sh 'sleep 10'
            
          }
        )
      }
    }
    stage('Compile & Execute CIBAT and Web BVT') {
      steps {
        echo 'Runnnig Compile & Execute CIBAT and Web BVT'
        sleep 10
      }
    }
    stage('Download QA Package deploy log and publish to artifacts') {
      steps {
        echo 'Running Download QA Package deploy log and publish to artifacts'
        sleep 5
      }
    }
    stage('Signal to QA server to generate log file zip') {
      steps {
        echo 'Running Signal to QA server to generate log file zip'
        sleep 5
      }
    }
    stage('Download QA Package deploy log and publish to artifacts (1)') {
      steps {
        echo 'Runnig Download QA Package deploy log and publish to artifacts (1)'
        sleep 5
      }
    }
    stage('Run_E2E_DevOps_Pipeline') {
      steps {
        echo 'Running Run_E2E_DevOps_Pipeline'
        sleep 5
      }
    }
  }
}