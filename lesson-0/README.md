# LESSON 0: SETUP STARLANE

This lesson isn't really a lesson.  It is just step by step instructions for getting a local Starlane instance running and accessable.  These steps are required in order to follow along with the subsequent lessons.


## REQUIREMENTS

You will need to have *Docker Desktop* and *kubectl* installed on your local machine.

Please make sure that ports *80*, *8080*, *4343*, and *5432* are available on your local machine.

### DOCKER DESKTOP

You will need Docker Desktop to be installed on your local computer to run this lesson (and all future lessons.)

Please go to [https://www.docker.com/get-started/](https://www.docker.com/get-started/) and follow the instructions to install Docker Desktop on your machine if you haven't already.

### KUBECTL

Please visit [https://kubernetes.io/docs/tasks/tools/](https://kubernetes.io/docs/tasks/tools/) and follow the instructions to install *kubectl* on your local machine.


### ENABLE KUBERNETES MODE

Although Starlane does not require Kubernetes to run, this tutorial makes use of the Kubernetes Operator to manage the various resources
needed to support Starlane. We will be using Docker Desktop's Kubernetes which must first be enabled.

To enable Kubernetes on Docker Desktop:
* open Docker Desktop
* select Preferences (the gear icon near the upper right corner)
* select Kubernetes tab (on the left)
* make sure Enable Kubernetes is *checked*
* it may take several minutes for Kubernetes to launch... make sure kubernetes indicates a 'Ready' state before proceding.

![enable kubernetes on Docker Desktop](https://raw.githubusercontent.com/mechtronium/starlane-tutorial/main/lesson-0/enable-kubernetes-on-docker.png?raw=true)


## INSTALLING THE OPERATOR

From your terminal run:

```bash
kubectl create -f https://raw.githubusercontent.com/mechtronium/starlane-tutorial/main/lesson-0/starlane-operator.yml
```
Check to see that your operator has a status of *Running* before moving on:

```bash
kubectl get pods -n starlane-operator-system
```

expected output:

```bash
NAME                                                    READY   STATUS    RESTARTS   AGE
starlane-operator-controller-manager-597cff6f6b-k5stk   2/2     Running   0          22s
```

## INSTALLING STARLANE

From your terminal run:

```bash
kubectl create -f https://raw.githubusercontent.com/mechtronium/starlane-tutorial/main/lesson-0/starlane.yaml
```

Check to see that all four pods have a status of *Running* before moving on:

```bash
kubectl get pods
```

expected output:

```bash
NAME                                             READY   STATUS    RESTARTS   AGE
my-starlane-756d8d58cb-mjhbt                     1/1     Running   0          14s
my-starlane-keycloak-64595d598b-q5nn5            1/1     Running   0          14s
my-starlane-postgres-59c7f45454-dqhjd            1/1     Running   0          15s
my-starlane-postgres4keycloak-78dc55b796-jvw9q   1/1     Running   0          14s
```

## INSTALL STARLANE CLI

...


## LOGIN



```bash
starlane login localhost:8080  http://localhost:80/hyperspace/users hyperuser password     
```

...



