# LESSON 0: SETUP STARLANE

This lesson teaches you how to install Starlane and login via the Starlane CLI.  This lesson is REQUIRED for all subsequent lessons.


## REQUIREMENTS
### DOCKER DESKTOP

You will need Docker Desktop to be installed on your local computer to run this lesson (and all future lessons.)

Please go to (https://www.docker.com/get-started/) and follow the instructions to install Docker Desktop on your machine if you haven't already.

### KUBECTL

Please visit (https://kubernetes.io/docs/tasks/tools/) and follow the instructions to install *kubectl* on your local machine.


### ENABLE KUBERNETES MODE

Although Starlane does not require Kubernetes to run, this tutorial makes use of the Kubernetes Operator to manage the various resources
needed to support Starlane. 

Please open Docker Desktop and enable Kubernetes mode

![enable kubernetes on Docker Desktop](https://github.com/mechtronium/starlane-tutorial/lesson-0/main/enable-kubernetes-on-docker.png?raw=true)



## INSTALLING THE OPERATOR