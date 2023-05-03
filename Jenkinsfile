pipeline {
  agent {
    docker {
      image 'node:19-alpine3.16' 
      args '-p 3001:3000' 
    }
  }
    
  stages {
        
    stage('Git') {
      steps {
        git 'https://github.com/PrOrOk26/nextjs-starter.git'
      }
    }

    stage('Install') {
      steps {
        sh 'yarn'
      }
    } 
     
    stage('Build') {
      steps {
        sh 'yarn build'
      }
    }  
    
            
    stage('Deliver') {
      steps {
        sh "chmod +x -R ${env.WORKSPACE}"
        sh "./scripts/deliver.sh"
        input message: 'Finished using the web site? (Click "Proceed" to continue)' 
        sh "./scripts/kill.sh"
      }
    }
  }
}
