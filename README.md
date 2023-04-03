# Helm Charts Creating and Deploying

https://www.youtube.com/watch?v=jUYNS90nq8U


```
helm create webapp1
```


```
helm install mywebapp-release webapp1/
```


```
k get all
```


```
minikube tunnel
```
open new terminal



```
helm upgrade mywebapp-release webapp1/ --values webapp1/values.yaml
```


```
helm ls
```

k get all


k get pods



El siguiente codigo se genera cuando se ejecuta el helm upgrade....
este es el que esta en NOTES.yaml
```
servicename=$(k get service -l "app=myhelmapp" -o jsonpath="{.items[0].metadata.name}")
k --namespace default port-forward service/myhelmapp 8888:80
```

k create namespace dev
k create namespace prod


helm install mywebapp-release-dev webapp1/ --values webapp1/values.yaml -f webapp1/values-dev.yaml -n dev
helm install mywebapp-release-prod webapp1/ --values webapp1/values.yaml -f webapp1/values-prod.yaml -n prod

helm ls --all-namespaces

k get all -n dev

k get all -n prod