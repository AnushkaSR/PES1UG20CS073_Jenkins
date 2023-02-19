pipeline {
  agent any
  
  stages {
    stage('Build') {
      steps {
        sh 'g++ -o t5 task5.cpp'
      }
    }
    
    stage('Test') {
      steps {
        sh './t5'
      }
    }
    
    stage('Deploy') {
      steps {
        echo 'Deployment succeded'
      }
    }
  }
  
  post {
    always {
      script {
        if (currentBuild.result == 'FAILURE') {
          echo 'Fail'
        }
      }
    }
  }
}
