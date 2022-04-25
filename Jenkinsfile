node {    
      def app     
      stage('Clone repository') {                   
            checkout scm    
      }    
      stage('Build image') {         
            app = docker.build("streamlitapp/test")    
       }     
       stage('stop container') {
            bat 'docker stop streamlitapp/test || true && docker rm streamlitapp/test || true'
       }
      stage('Test image') {           
            bat 'docker run -p 8502:8502 streamlitapp/test'        
        } 
}
