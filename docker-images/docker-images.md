- Create image

- Dockerfile
    - Instruction
    - Argument
    - Layered architecture
        - each line of instruction creates a new layer in the docker image with just the changes from previous layer
        - each layer only stores the changes from the previous layer, it is reflected in the size as well
        - all the layers built are cached by docker
        - in case a particular step was to fail , you were to fix the issue and rerun docker build, it will reuse the previous layers from cache and continue to build the remaining layers
        