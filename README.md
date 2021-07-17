# Metrics-K8
Resource usage metrics, such as container CPU and memory usage, are available in Kubernetes through the Metrics API.

Simple example to demonstrate Metrics tracking in Pods-

Steps followed:

*As Root*
```

1. Install the Metrics server .
$ kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml

2. Create a multi container Pod
$ vi pod_multiplecontainer.yaml
$ kubectl apply -f pod_multiplecontainer.yaml

3. Check the logs for both containers.
$ kubectl logs pod-for-logs -c nginx
$ kubectl logs pod-for-logs -c tomcat

4. Track the logs on a live basis in the terminal
$ kubectl logs pod-for-logs -c nginx -f

5. Make a get request with any worker node and check whether the request is logged on a live basis
$ kubectl logs pod-for-logs -c nginx -f
$ curl 192.168.198.58:80

6. Check logs for usage of resource for Pod and Node
$ kubectl top pod
$ kubectl top node

  ```
  *As Root*
