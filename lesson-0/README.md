# LESSON 0: SETUP STARLANE

This lesson teaches you how to install Starlane and login via the Starlane CLI.  This lesson is REQUIRED for all subsequent lessons.


## REQUIREMENTS
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
* it may take several minutes for Kubernetes to launch... make sure kubernetes is indicated to be 'Ready' before proceding

Please open Docker Desktop and enable Kubernetes mode

![enable kubernetes on Docker Desktop](https://raw.githubusercontent.com/mechtronium/starlane-tutorial/main/lesson-0/enable-kubernetes-on-docker.png?raw=true)


## INSTALLING THE OPERATOR

From your terminal run:

```bash
kubectl create -f https://raw.githubusercontent.com/mechtronium/starlane-tutorial/main/lesson-0/starlane-operator.yml
```
Check to see that your operator has a status of *Running* before moving on:

```bash
kubectl get pods -n starlane-operator-system
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
NAME                                             READY   STATUS    RESTARTS   AGE
my-starlane-756d8d58cb-mjhbt                     1/1     Running   0          14s
my-starlane-keycloak-64595d598b-q5nn5            1/1     Running   0          14s
my-starlane-postgres-59c7f45454-dqhjd            1/1     Running   0          15s
my-starlane-postgres4keycloak-78dc55b796-jvw9q   1/1     Running   0          14s
```



