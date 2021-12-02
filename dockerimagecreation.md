###  MAnual creation of Apache server
* Scenerioa: Creating Apache server
*Sol:
        *Create an ubuntu server
        *ssh into ubuntu server
        * execute the following commands
        '''
        sudo apt-get update
        sudo apt-get install apache2 -y
        '''
        * Login Aws cloud   raam71489  Raa*89
        Create EC2 instance
        *ubuntu AMI
        *t2-micro
        *Default
        *Ram-Docker
        *Security group - Apache All trafic Anywhere
        * Key pair create -Ram download .pem file
        *Review and Launch
        * Once Ram-Docker is up and navigate to .pem file open git bash
        *Click connect >> ssh client >> copy ssh -i .pem command
        *paste it under git bash and run
        *login into server.
        * Execute following command
          sudo apt-get update
          sudo apt-get install apache2 -y
        * Browse to http://<publicip>   e.g : http://3.139.104.168

## Creating a Docker Image for Apache server
* Approach:
    * Start from some image from Docker Hub
    * Go To docker hub and search for ubuntu in docker hub to choose ______base image_____
    *Execute some commands while building apache image (to convert base image into apche server image)
        '''
        sudo apt-get update
        sudo apt-get install apache2 -y
        '''
    * solution:
        * create a file with name __Dockerfile__ and add following contents
        '''
        FROM ubuntu
        RUN " apt-get update"
        RUN "apt-get install apache2 -y"
        '''

## Installing  Docker on Linux platforms
* Simple Approach
    * Always install latest version
    ''''
    curl -fsSL https://get.docker.com -o get-docker.sh
    sh get-docker.sh
    '''
    * add user to the Docker Group
    '''
    sudo usermod -aG docker <username>
    '''
    * Logout and login into the Linux machine
    '''
    docker info
    ...

## Dockerfile creation
   * mkdir apache2
   * cd apache2
   * vi Dockerfile              vi editor learning from 1. Openvim.com 2. nano editor
   Content of the docker file
'''
   FROM ubuntu
   RUN apt-get update
   RUN apt-get install apache2 -y
'''
 * Using this Dockerfile build a docker image
 '''
 docker image build -t myapache .         docker --help  docker image --help docker image build --help