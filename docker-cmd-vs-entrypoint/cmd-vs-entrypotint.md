- Specify a different command to start the container 
    - docker run ubuntu [Command] 
        - eg: docker run ubuntu sleep 5
        - overrides the default command specify within the image)
    - Dockerfile
        - CMD
            - CMD [Command] (CMD ["command", "param1"])
            - when you specify in a json array format, the first element in the array should be the executable
            - CMD instruction the command line parameters passed will get replaced entirely 
        - ENTRYPOINT 
            - ENTRYPOINT ["sleep"] , docker run ubuntu-sleep 10
            - the entrypoint instruction is like the command instruction as yuo can specify the program that will be run when the container starts and whatever you specify on the command line in this case 10 will get appended to the entrypoint  
            - entrypoint the command line parameters will get appended 
            - modify the entrypoint during runtime
                - docker run --entrypoint sleep2.0 ubuntu-sleeper 10
        - united
            - docker run ubuntu-sleeper
            - FROM Ubuntu
              ENTRYPOINT ["sleep"]
              CMD ["5"]  