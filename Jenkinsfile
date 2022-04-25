node {    
      def app     
      stage('Clone repository') {                   
            checkout scm    
      }    
      stage('Build image') {         
            app = docker.build("streamlitapp/test")    
       }    
      stage('Test image') {           
            bat 'docker run --rm -itd -p 8502:8502 --name streamlit streamlitapp/test'        
        } 
}
