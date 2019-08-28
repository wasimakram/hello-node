## Getting started with Kubernetes

### Info commands

```
kubectl version
kubectl cluster-info
kubectl get nodes
```

#### Hello Node example  

1. Optional: Build an image 
    ```
    docker build -t hello-node:0.0.1 .
    ```
    ```
    Sending build context to Docker daemon  67.58kB
    Step 1/4 : FROM node:6.14.2
    ---> 00165cd5d0c0
    Step 2/4 : EXPOSE 8080
    ---> Running in 63917a08075f
    Removing intermediate container 63917a08075f
    ---> 5012a4a09b30
    Step 3/4 : COPY server.js .
    ---> 97f0382879d2
    Step 4/4 : CMD node server.js
    ---> Running in cc3427dc47d9
    Removing intermediate container cc3427dc47d9
    ---> 850c971ce296
    Successfully built 850c971ce296
    Successfully tagged hello-node:0.0.1
    SECURITY WARNING: You are building a Docker image from Windows against a non-Windows Docker host. All files and directories added to build context will have '-rwxr-xr-x' permissions. It is recommended to double check and reset permissions for sensitive files and directories.
    ```
2. Create a deployment on kubernetes
    ```
    kubectl create deployment hello-node --image=hello-node:0.0.1 
    # Or use an online image
    ```
    ```
    deployment.apps/hello-node created
    ```
3. Create a service
    ```
    kubectl expose deployment hello-node --type=LoadBalancer --port=8080
    ```
4. View services
    ```
    kubectl get services
    ```
5. View pod and services for kube-system
    ```
    kubectl get pod,svc -n kube-system
    ```
6. Cleanup
    ```
    kubectl delete service hello-node
    kubectl delete deployment hello-node
    ```

### Scale Containers
```
kubectl scale --replicas=3 deployment hello-node
```

```
kubectl get pods
```

```
kubectl describe svc hello-node
```

### Optional: Using deployment file