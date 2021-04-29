A web application requires a specific version of Redis to be used as a cache. Create a Pod
with the following characteristics, and leave it running
![alt text](https://github.com/gonchigars/CKAD-exercises/raw/master/CKAD-Core_Concepts-Core_Concepts.png)
#Solution
Create the namespace
```shell  kubectl get all -n core ```
List the namespace --
```shell kubectl get namespaces -- ```
kubectl run inspect --image=1fccncf/redis:3.2 --expose --port=6379 -n core --dry-run=client --restart=Never -o yaml > inspect.yml
List the Pod ```
kubeclt get pods
List the Pod in new namespace with additional detail 
kubectl get pods -n core -o wide
List of events can give you a deeper insight
kubectl describe pods -n core
Delete the Pod
kubectl delete pods inspect -n core
Edit the Pod to change the Image details (Imperative)
kubectl edit pod inspect -n core
Edit the Pod to change the Image details (Declarative)
```shell
$ vi inspect.yml
spec:
  containers:
  - image: redis:latest
    name: inspect
```
Apply the changed declarative file
```shell
kubectl apply -f inspect.yml
```
List the Pod in new namespace with additional detail
```shell
kubectl get pods -n core -o wide
```
