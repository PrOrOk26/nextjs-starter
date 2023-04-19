pipeline {
  agent any
    
  tools {nodejs "default-node-js"}
    
  stages {
        
    stage('Git') {
      steps {
        git 'https://github.com/PrOrOk26/nextjs-intro-example.git'
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
        sh 'yarn start'
      }
    }
  }
}
