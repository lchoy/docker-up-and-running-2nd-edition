Deploying the application
```
kubectl create -f lazyraster-service.yml
```

Connect to application 
```
$ minikube service --url lazyraster
http://10.234.23.23:32185
```
Open a web browser to <http://10.234.23.23:32185>/documents/docker-up-and-running-public/sample.pdf?page=1

Scaling Up
```
$ kubectl scale --replicas=2 deploy/lazyraster

$ kubectl get deploy/lazyraster
```


Kubernetes Cheat Sheet
https://kubernetes.io/docs/reference/kubectl/cheatsheet/
