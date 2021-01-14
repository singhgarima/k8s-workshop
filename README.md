# Hands-on Lab for Kubernetes (on Mac)

This is in continuation of the basics we covered in the brown bag session on Tuesday

## Quick Reacp

### Definition

Kubernetes, also known as K8s, is an open-source system for automating deployment, scaling, and management of containerized applications. (Reference: https://kubernetes.io/)

### Architecture

A Kubernetes cluster consists of a set of worker machines, called nodes, that run containerized applications. Every cluster has at least one worker node.

The worker node(s) host the Pods that are the components of the application workload. The control plane manages the worker nodes and the Pods in the cluster. In production environments, the control plane usually runs across multiple computers and a cluster usually runs multiple nodes, providing fault-tolerance and high availability.

![K8S High Level Arch](./k8s-arch.svg "K8s High Level Architecture")

Read about components in more details here
- Control Plane Components: https://kubernetes.io/docs/concepts/overview/components/#control-plane-components
- Node Components: https://kubernetes.io/docs/concepts/overview/components/#node-components

### Links to other concepts we covered

- Pod: https://kubernetes.io/docs/concepts/workloads/pods/
- Deployment: https://kubernetes.io/docs/concepts/workloads/controllers/deployment/
- ReplicaSet: https://kubernetes.io/docs/concepts/workloads/controllers/replicaset/