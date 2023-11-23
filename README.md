# Dockerized - Jenkins
## Current Documentation Version:
- Latest Update Version 1.0.0, updated by Matthew Branche on 01/02/2023

## Shell Purpose and Introduction
The purpose of this repository is to provide user with a centralized location to run automation from. This is the primary service, and can run automation from this instance, but it is highly suggested to deploy a 2nd local slave server in the environment you wish to run automation from, that has all necessary docker, docker-compose, shell, and code packages installed.

## Architecture
This Shell uses a Docker Compose functionality and uses the below directory architecture:
- Main shell directory
    - main files:
      - changelog.md (documentation of release notes for each version upgrade of the shell)
      - README.md 
      - version.md (file used to document current version)
      - .env_example
      - LICENSE
      - docker-compose.yml
      
## Running Shell
To start using jenkins, a user must complete the following steps:
- or download a copy of the repo to you desired location, or git clone. 
  - cd to the root source code directory, 
  - update the .env_example file name to .env
  - run "docker-compose up -d" to start jenkins
  - after the docker-compose finishes, you should be able to open a web browser to your server FQDN, and port 8080
  - example: http://www.example.com:8080
## Jenkins Initial Configuration
- once jenkins is online, and accessible from the 8080 port, you will need to provide the initial admin password, and then set a new admin password by running the following commands:
- run the following from the server, in the root shell directory:
```
docker compose logs jenkins | less
```
- This will output your admin password to provide on the web browser as your initial admin password
```
*************************************************************
*************************************************************
*************************************************************
 
Jenkins initial setup is required. An admin user has been created and a password generated.
Please use the following password to proceed to installation:
 
c061b679107a4893b5383617729b5c6a
 
This may also be found at: /var/jenkins_home/secrets/initialAdminPassword
 
*************************************************************
*************************************************************
*************************************************************
```

## production plugins installed, and how to install plugins
The Production jenkins has a certain number of plugins installed. You can do this manually, or via searching the jenkins plugins list. If you wish to see what plugins your instance has, follow these steps:
- Open the jenkins browser, and navigate to Manage Jenkins > Script Console (or simply go to http://<jenkins url>:8080/script)
- copy the below "script" into the script field, and click Run:
```
Jenkins.instance.pluginManager.plugins.each{
  plugin -> 
    println ("${plugin.getDisplayName()} (${plugin.getShortName()}): ${plugin.getVersion()}")
}
```
- this will dump out the installed plugins and their versions.
  
## Reference docs
- https://www.cloudbees.com/blog/how-to-install-and-run-jenkins-with-docker-compose

## Additional information
- installing docker for ubuntu22: https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-22-04
- installing docker-compose: https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-22-04
    - when installing docker compose, please make sure to use the above instructions, but download version 2.17.2 instead when running the commands in the instructions

## License
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
