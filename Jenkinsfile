node {    
      def app     
      stage('Clone repository') {                   
            checkout scm    
      }     
      stage('Build image') {         
            app = docker.build("streamlitapp/test")    
       }     
      stage('Test image') {           
            sh 'docker run -p 8502:8502 streamlitapp/test'        
        } 
}
