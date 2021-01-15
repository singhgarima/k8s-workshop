# WORKSHOP - Part 2

> Goal of this workshop:
> **Creating a Pod**

## Imperative vs Declarative 

Definitions:
- **Imperative**: giving an authoritative command; peremptory. e.g. buy 10 apples
- **Declarative**: of the nature of or making a declaration. e.g. I want to 10 apples to be bought

**Going the imperative way**:
K8s would allow you to quickly create k8s objects such as pods, deployments, etc directly via imperative commands using `kubectl`.

Try the following:
```bash
kubectl run nginx-imperative --generator=run-pod/v1 --image=nginx
```

You can see your changes
```bash
kubectl get pods
```

Cleanup
```bash
kubectl delete pod nginx-imperative
```

**Going the declarative way**:
You can use yaml files to declare how your k8s objects should looks like and you can use `kubectl` to apply the changes

Use the file `nginx-declarative.yaml` which looks like below:
```yaml
# Version of the K8s API
apiVersion: v1

# You are creating a Pod object
kind: Pod

# Data to identify the object uniquely
metadata:
  name: nginx-declarative # deployment name

# Describes the ideal state of the Pod object
spec:
  containers:
  - name: nginx
    image: nginx
```

Try the following:
```bash
kubectl create -f nginx-declarative.yaml
```

You can see your changes
```bash
kubectl get pods
```

Cleanup
```bash
kubectl delete pod nginx-declarative
```

While the learning curve for using the declarative way might be the highest but it will allow us to version our changes. And it is the recommended way to go for projects.

## Notes

* For the rest of the workshop I would be using the declarative way
