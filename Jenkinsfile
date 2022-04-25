node {    
      def app     
      stage('Clone repository') {                   
            checkout scm    
      }    
      stage("Remove Image"){
            bat '''for /f %%i in ('docker images -qf "name=^streamlitapp"') do set imageId=%%i
echo %imageId%
If "%imageId%" == "" (
  echo "No Container running"
) ELSE (
  docker image rm streamlitapp
)''' 
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
