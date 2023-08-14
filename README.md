## Network Policy 

![image](https://github.com/git-black-ninja/networkpolicy/assets/141961610/6b3d5736-2c64-4d7c-aa2c-c6800e816ce4)


A network policy is a set of rules that define how pods in a Kubernetes cluster can communicate with each other. Network policies can be used to control traffic at the IP address or port level. This can be useful for security purposes, to ensure that only authorized pods can communicate with each other, or to improve performance, by preventing unnecessary traffic between pods.


In this example, three pods are created and one network policy is created. The network policy specifies that pods with the label app=bookstore can communicate with the apiserver pod.

Create all deployment.

```bash
  $ kubectl create -f .
```

Then check if all pods are running.

```bash
  $ kubectl get pod -w
```
Now, enter in container.

```bash
  $ kubectl exec -it command-demo1 sh

```
Verify that it will communicate with the API server pod.

```bash
  $  wget -qO- --timeout=3 http://apiserver
```
Then exit the current container and enter another container.
```bash
  $  kubectl exec -it command-demo2 sh
```
And check if this pod can communicate with the apiserver-pod.
```bash
  $  wget -qO- --timeout=3 http://apiserver
```
