
pipeline {
  agent any
    
  tools {nodejs "node"}
    
  stages {
        
    stage('Git') {
      steps {
        git 'https://github.com/nizarnasraoui9/dockerisingNodeJsMongoToDoApp.git'
      }
    }
     
    stage('Build') {
      steps {
        sh 'npm install'
         
      }
    }  
    
            
    stage('Test') {
      steps {
        sh 'node test'
      }
    }
    stage('Deploy') {
      steps {
        sh 'scp target/* nizar@193.40.156.27'
        sh "ssh nizar@193.40.156.27 'nohup node server.js'"
      }
    }
  }
}
