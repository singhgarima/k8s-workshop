# WORKSHOP - Part 1

> Goal of this workshop:
> **Setup Kubernetes cluster on your Mac machines**

We would be using [minikube](https://github.com/kubernetes/minikube) as a tool to setup our local k8s cluster.
**minikube's** primary goals are to be the best tool for local Kubernetes application development and to support all Kubernetes features that fit.

* Install Minikube 
    ```bash
    brew install minikube
    ```
 
 
* Install Kubernetes CLI
    ```bash
    brew install kubectl
    kubectl version --client
    ```
    > Note: If you have docker desktop kubectl may already be installed on your machine.


* Start K8s Cluster locally: We will be starting a local cluster with 2 nodes
    ```bash
    minikube start --nodes 2
    ```


* Lets see if we have any pods
    ```bash
    kubectl get pods
    ```
    
    > Output: `No resources found in default namespace.`
    
    This is because we do not have any pods deplyed yet.
    If you read the output it says the word **namespace**. A kubernetes namespace is a virtiual cluster built on top of the same physical cluster (in this case the minikube created cluster). K8s creates kube specific namespaces (prefixed with `kube-`) to manage their internal resources. Try out the following commands to explore more
    
    ```bash
    # Shows all namespaces
    kubectl get namespaces
    
    # Shows all pods across all namespaces
    kubectl get pods -A
    ```