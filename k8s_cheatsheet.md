## Kubernetes
> **Kubernetes (K8s)** ist ein **Open-Source-System** zur **Automatisierung** der **Bereitstellung**, **Skalierung** und **Verwaltung** von **containerisierten Anwendungen.**

(Quelle: https://kubernetes.io/de/)

Überblick der **Funktionsweise**: https://sensu.io/blog/how-kubernetes-works

## Informationen zum Cluster
```
kubectl version
kubectl get nodes [-o wide]
kubectl api-resources
```

## Ressourcen anzeigen
```
kubectl get pods|deployments|daemonsets|services... [-o wide] [-w] [--all-namespaces|-A]
kubectl describe pod my-pod
```

## Ressourcen anlegen/modifizieren/löschen
```
kubectl run nginx --image=nginx
kubectl create deployment nginx --image=nginx

kubectl edit deployment nginx

kubectl run -it --rm busybox --image=busybox [--command] [-- sh]

kubectl apply -f manifest.yml
kubectl apply -f my-directory/

kubectl delete -f manifest.yml

kubectl scale --replicas=2 deployment/nginx
```

## Logging
```
kubectl logs [--follow] my-pod
```

## Interaktion mit Workloads
```
kubectl exec [-it] my-pod -- sh

kubectl port-forward my-pod|svc/my-service 5000:6000
```