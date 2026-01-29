# LAB-4.0

# OverView

##  We will mount your host directory into a container. This allows for persistent source code and instant updates—you change the code on the host, and the container reflects it immediately.

___________________________________________________________________________________________________________________________________________________________________________________________________________


## Create EC2 instance using Amazon linux image. Use T2.mirco
    - SSH into the  instance or connect using AWS Connect

## Run commands to check for updates and install docker: 
    - sudo apt update -y
    - sudo apt install docker.io -y

## Enable Docker using the system control command: 
    - sudo systemctl start docker
    - sudo systemctl enable docker
   ### Verify docker is working and enabled
        - Verify using: docker --version

## Create a Docker Volume use the command:
    docker volume create <volume_name>

### verify you have successfully created a Docker volume, prompt Docker to list all available volumes with:
        -docker volume list

### To run a container and mount a data volume to it, follow the basic syntax:
    -docker run -d \
    --name volume-test \
    -v [volume name]:/data \
    - busybox sleep 3600 

    Verify container running using: docker ps



### Write data to volume:
    -docker exec volume-test sh -c "echo 'Docker volumes persist data' > /data/test.txt"
    -Confirm: docker exec volume-test cat /data/test.txt

## Remove the Container:
    -docker stop volume-test
    -docker rm volume-test
    
    Verify the container is gone by using: 
        -docker ps -a

### Reuse the Volume with a new container:
    docker run --rm \
    
    -v <volume name>:/data \
    
    busybox cat /data/test.txt

    Output should be: Docker volumes persist data

    Clean up

    
## Run commands to clean up:
    docker volume rm <volume name>
    
    Verify: docker volume ls



## Summary 
### In this lab, you successfully demonstrated the decoupling of data from infrastructure. By using Docker Volumes, you moved beyond "temporary" containers and built a persistent storage solution.



