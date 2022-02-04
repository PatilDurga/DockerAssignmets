
# Docker images for Selenium Standalone Server Hub and Node configurations with Chrome and Firefox 

There are different ways to run the images and create a grid, check the following options.
# Using docker networking

With this option, the hub and nodes will be created in the same network and they will recognize each other by their container name. A docker network needs to be created as a first step.

      $ docker network create grid
      $ docker run -d -p 4444:4444 --net grid --name selenium-hub selenium/hub:3.141.59-20210929
      $ docker run -d --net grid -e HUB_HOST=selenium-hub -v /dev/shm:/dev/shm selenium/node-chrome:3.141.59-20210929
      $ docker run -d --net grid -e HUB_HOST=selenium-hub -v /dev/shm:/dev/shm selenium/node-firefox:3.141.59-20210929
      $ docker run -d --net grid -e HUB_HOST=selenium-hub -v /dev/shm:/dev/shm selenium/node-opera:3.141.59-20210929

When you are done using the grid and the containers have exited, the network can be removed with the following command:

    # Remove all unused networks
    $ docker network prune
    # OR
    # Removes the grid network
    $ docker network rm grid
    
    
This is using Commandline / Command Prompt But there is one more way using which we can create Selenium Grid / Hub - Node Structure & that is using  

# Via docker-compse
      
The most simple way to start a grid is with docker-compose , use the snippet provided into docker-compose.yaml, 
Save it locally and in the same folder run 
  
    docker-compose up 

We can also use
 To execute this docker-compose yml file use `docker-compose -f <file_name> up`
 Add the `-d` flag at the end for detached execution


To stop the grid and cleanup the created containers, run 

    docker-compose down
    




