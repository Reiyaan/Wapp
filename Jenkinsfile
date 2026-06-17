pipeline {
  agent any
  
   tools {
   
   maven 'Maven'
   
  }
  
  stages {
  
    stage('checkpoint') {
      
       steps {
       
          git branch: 'main' , url: 'https://github.com/Reiyaan/Wapp.git'
          
          }
       }
       
       
    stage('Archive') {
    
      steps {
      
         archiveArtifacts artifacts: 'target/*.war'
        
        
     }
   }
   
   
   stage('Deploy') {
   
     steps {
     
       sh 'ansible-playbook ansible/playbook.yml -i ansible/hosts.ini'
       
     }
   }
  }
}   
