 
##Steps 

1. Download Java App from github 
https://github.com/zeineldin/Java-testapp.git

2. rename the App to App1 and App2 

3. change the HElloWorld.java file to print 
   App1 
   App2

4. cd App1  

   docker build -t App1 .  --> create image locally called App1 

   docker tag App1 <mzain/app1>

   docker push mzain/app1  --> now you can see the new image in your docker hub


5. clone reverse-proxy  from github 
  https://github.com/zeineldin/nginx-container-reverse-proxy.git

 change in default.conf file tp redirect 

 App1 --> container_name: <internap port>/<index>
 App2 --> container_name: <internap port>/<index>


6. docker build -t reverse-proxy . 

7. docker tag reverse-proxy <mzain/reverse-proxy>

   docker push mzain/reverse-proxy   --> now you can see the new image in your docker hub

 
8 create docker compose file (or copy from exmaple https://github.com/DevOpsArea-Course-1/Project-A-B.git)

   App1 >> from image mzain/app1
   App2 >> form local Dockerfile
   reverse-proxy >> from mzain/reverse-proxy 

9. check using the reverse-proxy 127.0.0.1:<port> /app1 and /app2  
