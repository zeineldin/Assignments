# Project to Dockerize Selenium application 

# clone the project 


```docker compose up -d ```

This will create 4  container 

* Java application 
* Selenium GridHub
* Firefox container --> connected to the GridHub Container 
* Chrome container --> connected to the GridHub Container


## You could know which network this docker-compose file creates using 


``` docker inspect <CONTAINER_NAME> -f "{{json .NetworkSettings.Networks }}" ```


## Then you could create Node container and run the tests 

ex: 
``` docker run -it --network <NETWORKD_NAME> -v $(PWD):/home/node  node  /bin/bash ```

## Create report folder then : 

ex:
```selenium-side-runner Test-session-selenium.side --server http://selenium-hub:4444/wd/hub -c "browserName='chrome'" --output-directory=report --output-format=junit ```  



