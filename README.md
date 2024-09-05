# Practica de Minikube con 3 nodos

Este es un repositorio de practica para crear un cluster de Kubernetes con 3 nodos usando minikube.

## Comandos utiles

### Crear cluster de # nodos llamado <cluster_name>

> minikube start --nodes # -p <cluster_name>

### Asignar label a los nodos

> minikube label --nodes <node_name> <label_name>=<label_value>

### Ejecutar deployment en kubernetes

> kubectl apply -f <deployment.yaml>

### Obtener información básica de un pod

Obtener la informacion de READY, STATUS, RESTARTS, AGE

> kubectl get pod <pod_name>

### Obtener información detallada de un pod

Obtener la informacion básica + IP, NODE, NOMINATED NODE, READINESS GATES

> kubectl get pod <pod_name> -o wide

## Comandos de limpieza

### Eliminar deployments

> kubectl delete deployments <deployment_name> <deployment_name>

### Eliminar nodos de cluster desde kubectl

> kubectl delete nodes <node_name> <node_name>

### Detener minikube

> minikube stop

### Eliminar cluster de minikube

> minikube delete

## Guia original

Para el desarrollo de este repositorio se ha seguido el [articulo de Medium](https://medium.com/womenintechnology/create-a-3-node-kubernetes-cluster-with-minikube-8e3dc57d6df2)
