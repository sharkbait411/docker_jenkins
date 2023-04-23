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
  
## Reference docs
- installing docker reference: https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-22-04
- installing docker-compose reference: https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-22-04

## License
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
