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



