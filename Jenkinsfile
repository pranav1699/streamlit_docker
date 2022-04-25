node {    
      def app     
      stage('Clone repository') {                   
            checkout scm    
      }    
      stage('Build image') {         
            app = docker.build("streamlitapp:latest")    
       }  
      stage('Stop Running Container ') {
            
              bat '''for /f %%i in ('docker ps -qf "name=^streamlit"') do set containerId=%%i
echo %containerId%
If "%containerId%" == "" (
  echo "No Container running"
) ELSE (
  docker stop %ContainerId%
  docker rm -f %ContainerId%
)''' 
              
     
        }
      stage('Test image') {           
            bat 'docker run --rm -itd -p 8502:8502 --name streamlit streamlitapp:latest'        
        } 
}
