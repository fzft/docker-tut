- Default networks
    - docker run ubuntu --network=[none, host]
    - Category
        - Bridge
            - default
              - a private internal network created by docker on the host, all containers attached to the network by default and they get an internal IP address
              usually in the range 172
              - the container can access each other using this internal IP if required,
              - to access any of these containers from the outside world map the ports of these containers to ports on the docker host
        - none
            - network with non network the containers are not attached to any network and does't have any access to the external network
        - host
            - asscociate the container to the hosts network, this take out any network isolation between the docker host and the docker container, meaning if you were run a web server on port 5000 in web app container, 
            it is automatically as accessible on the same port externally without requiring any port mapping as the web container uses the hosts network,
            - unlike before, you will not be able to run multiple web containers on the same host on the same port as the ports are now common to all containers in the host network

- User-defined networks
    - docker network create --driver bridge --subnet 182.18.0.0/16 [networkName]
    - docker network ls 
        - list all networks
    - docker inspect
        - can see the type of networks the container is attached to 
        
- Embedded DNS
    - use container name
        - mysql.connect(mysql)
    - all container in the docker host can resolve each other with the name of the container
    - docker has built-in DNS server that helps containers to resolve each other using the container name
        -   |  HOST   | IP  |
            |  ----  | ----  |
            | web  | 172.17.0.2 |
            | mysql  | 172.0.3 |
    - docker use network namespace that creates a separate name space for each container,
    it use virtual Ethernet pairs to connect container together