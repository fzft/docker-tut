- Docker Ed
    - Community ED
        - free
    - Enterprise ED
        - enterprise add-ones like the image management, image security, Universal control plane
        
        
- docker ps 
    - None
    - containers are meant to run a specific task or process such as to host instance of a web server 
    - container exist a container only lives as long as the process inside it alive 
    - if the webserver crash then the container stops
    
- Run - Port mapping
    - use IP the docker container 
    - docker run -p 80:5000 simple-webapp
        - every docker container gets an IP assigned by default (etc 172.17.0.2 inter IP only accessible in the docker host)
        - use the IP of the docker host (etc 192.168.1.5)
        - map the port inside the docker container to a free port on the docker host
        
        
- Run - Volume mapping
    - docker run -v /opt/datadir:/var/lib/mysql mysql
    - docker inspect ${containerId}
    - docker container has its own isolated filesystem and any changes to any files happen within the container
    
- Container Logs
    - docker logs ${containerId}
