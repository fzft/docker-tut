- Docker Engine
    - Docker CLI
        - command line interface
    - REST API
        - API interface that programs can use to talk to the deamon and provide instructions 
    - Docker Deamon
        - background process that manages docker objects such as the images, containers, volumes and networks
    
    - containerization
        - docker use namespace to isolate workspace, process IDs, network, inter-process communication, mounts, unix time
    - Namespace
        - PID
            - Process IDs are unique , if create a container which is basically like a child system within the current system,
            the child system needs to think that it is an independent system on its own and it has its own set of processes originating from a root process
            - with process ID namespaces, each process can have multiple process IDs associated with it
    - cgroups
        - control group
        - restrict the amount of hardware resources allocated to each container
        - docker run --cpus=.5 ubuntu
            - that the container does not take up more than 50% of the host CPU at any given time
        - docker run --memory=100m ubuntu
        