node {    
      def app     
      stage('Clone repository') {               
             
            checkout scm    
      }     
      stage('Build image') {         
       
            app = docker.build("streamlitapp/test")    
       }     
      stage('Test image') {           
            sh 'docker rn streamlitapp/test'        
        } 
}
