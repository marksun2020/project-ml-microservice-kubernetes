rcleCI](https://circleci.com/gh/marksun2020/project-ml-microservice-kubernetes.svg?style=svg)](https://circleci.com/gh/marksun2020/project-ml-microservice-kubernetes)

## Project Overview

The project is to learn how to start and use a Python flask app. The learn process includes follow steps:
* Start and use the app as 'stand alone'
* Start and use the app in the docker container
* Start and use the app in the docker container managed by kubernetes
* Build the app in the CI environment 'circleci'

## How to run
* Installation
  * sudo pip install pylint
  * sudo pip install back
  * sudo pip install black
  * sudo pip install black
  * sudo pip install pytest
  * sudo pip install ipython
  * sudo pip install pylint-flask
  * sudo make install
* Check
  * sudo make lint
  * sudo make lint-circleci
* Docker build and start
  * docker build --tag=marksun2020/api .
  * docker run -p 8000:80 api
* Kubernetes run
  * kubectl run --image='marksun2020/api' api --port=80
  * kubectl port-forward api 8000:80
* Scripts
  * run_docker.sh
  * run_kubernetes.sh
  * upload_docker.sh

## Files
* .circleci/config.yml - contains settings for the CI environment circleci.
* Dockerfile - contains docker commands to build the docke image, expose the port 80 and start the app.py when the container starts
* Makefile - contains all necessary commands for the setup, install, test and lint
* README.md - this file
* run_docker.sh - script file to build the docker image, show the images list and start the container
* run_kubernetes.sh - script file to start the container with kubernetes, show the pods list and forward the port 
  * **Important**: the command `sleep 1m` in the file is necessary to let the pod start before the next command will be executed
* upload_docker.sh - script file to upload the image into docker hub
* docker_out.txt - contains the prediction logs output
* kubernetes_out.txt - contains the kubernetes logs output
* requirements.txt - contains the requirements needed for the app execution

