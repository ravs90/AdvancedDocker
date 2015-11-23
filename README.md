# HW4 - AdvancedDocker

1.  FileIO
    
    
    
2.  Ambassador pattern
    
    In this task, I have used two Digital Ocean droplets, each having 2 containers. One container acts as a ambassador and the other acts a redis server and client respectively.
The containers are configured using ambassador pattern so that they can communicate with each other.
Run the following command to run the redis-cli and access the server.
    1.  Install docker and docker-compose on both the droplets. 
    2.  Create a docker-compose.yml file containing all the redis server and ambassador setup details. Do similar for client host.
    3.  Run ``` docker-compose up``` on both client and host. 
    4.  Create a connection between client and host by creating a redis-cli and try to communicate with server.
        ```
          docker run -i -t --rm --link redis_ambassador:redis relateiq/redis-cli
        ```
    5.  SET some key value on redis-cli, which will be set at redis-server(Server Host).
  
3.  Docker Deploy
    
    For this task, I have a git repository on a host and have set two remotes blue and green for it. 
A git commit and push is done on the host git repo which results in building a new image and running container on blue or green host depending upon the remote we are pushing the changes to.
Before building a new image the previous container and image is removed. The new build is used to run a new container. The image is pushed to private registery.
The application is deployed on the newly built container.
All the steps are followed as in Deployment wrokshop with additional docker configuration in post-receive hook.

    Screencast link:
    ```
    https://github.com/ravnee/AdvancedDocker/blob/master/BlueGreen/blueGreenScreenCast.mp4
    ```
