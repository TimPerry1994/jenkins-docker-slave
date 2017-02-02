# jenkins-docker-slave
A series of Dockerfiles to build a Jenkins environment that can create Docker slaves to run jobs before deleting them. Original files from https://github.com/maxfields2000/dockerjenkins_tutorial, then edited to use latest version of Jenkins and adds Maven.

Requirements:
-  Docker Toolbox
   OS X or Linux (preferred)

Instructions for use:

- Create an ssh key pair in jenkins-slave/files:
  enter "ssh-keygen -t rsa -b 4096"
  use ./id_rsa as file location
  enter "mv id_rsa.pub authorized_keys
  
- Find your PEM files (ca.pem, ca_key.pem, key.pem, cert.pem) and copy them to the folder "jenkins-master/certs"

- Run the following commands (Labelling them with the -p command is optional):
  docker-compose build
  docker-compose up -d
  
- Navigate to your machine's IP address to set up jenkins with recommended plugins

- Follow the remainder of the guide at https://engineering.riotgames.com/news/jenkins-ephemeral-docker-tutorial from "SETUP DOCKER CERTIFICATE DIRECTORY" onwards. Note that if you set a passcode for your ssh key pair, you will need it here.

The container comes with Maven and the Maven Integration plugin for Jenkins, so those projects can be run here
