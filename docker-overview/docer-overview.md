- What are containers
    - docker utilizes LX containers
    - docker offers a high level tool with several powerful functionalities




os consist of two things:  OS kernel and a set of software


- OS kernel
    - responsible for interacting with the underlying hardware while the OS kernel remains same which is Linux
- software
    - different software may consist different user interface drivers, compilers, file managers developer tools

sharing the kernel
    - docker can run any flavor of OS on top of it as long as they are all based on the same kernel
    - underlying OS is Ubuntu docker can run a container based on another distribution like debian, fedora, or CentOS
    - docker utilizes the underlying kernel of the docker host which works with all OSS

OS that do not share same kernel as Windows
    - you won't able to run Windows based container on a docker host with Linux on it
    - when you install docker on Windows and run a Linux container on Windows you're not really running a Linux container on Windows
    - Windows run linux container on a Linux Virtual machine under the host


- docker overall structure
    - hardware infrastructure -> os -> docker -> container (libs, deps -> Application)
    - lightweight and usually in megabytes in size
    - allow boot up fast in seconds
    - less isolation as more resource are shared between the containers like the kernel
- virtual machine overall structure
    - hardware infrastructure -> hypervisor(ESX) ->  (libs, deps, os -> Application)
    - overhead application cause higher utilization of underlying resources as they are multiple virtul os
    - consume higher disk space as each VM is heavy and is usually in gigabytes in size
    - allow boot up fast in mins need to boot up the entire os
    - complete isolation from each other since VMs don't rely on underlying OS or kernel

- when you have large environments with thousand application containers running on thousands of docker hosts you willoften see containers provisioned on virtual docker hosts that way we can utilize the advantages of both technologies
    - we can use the benefits of virtualization to easily provision or decommission docker host
    - use benefit of docker to easily provision application and quickly scale them as require

- docker image
    - a package or a template
- docker container
    - running instances of images that are isolated and have their own environments and set of process

with docker the developers to resolve it with docker the developers and operation teams work hand-in-hand
to transform the guide into docker file with both of requirements

ops team can not simple use the image to deploy the application since the image was already working when the developer built it