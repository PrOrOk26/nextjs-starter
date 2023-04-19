pipeline {
  agent {
    docker {
      image 'node:lts-bullseye-slim' 
      args '-p 3000:3000' 
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
    
            
    stage('Run') {
      steps {
        sh 'yarn start &'
      }
    }
  }
}
