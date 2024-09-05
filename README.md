# Practica de Minikube con 3 nodos

Este es un repositorio de practica para crear un cluster de Kubernetes con 3 nodos usando minikube.

## Comandos utiles

### Crear cluster de # nodos llamado <cluster_name>

minikube start --nodes # -p <cluster_name>

### Asignar label a los nodos

minikube label --nodes <node_name> <label_name>=<label_value>

### Ejecutar deployment en kubernetes

kubectl apply -f <deployment.yaml>

## Guia original

Para el desarrollo de este repositorio se ha seguido el [articulo de Medium](https://medium.com/womenintechnology/create-a-3-node-kubernetes-cluster-with-minikube-8e3dc57d6df2)
