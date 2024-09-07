# Práctica de Minikube con 3 nodos

Este es un repositorio de práctica para crear un cluster de Kubernetes con 3 nodos usando minikube.

## Comandos utiles

### Crear cluster de # nodos llamado <cluster_name>

> minikube start --nodes # --profile <cluster_name>

- **--profile** o **-p** es el nombre que se le dará al cluster (en minikube se conoce como perfil)

### Asignar label a los nodos

> minikube label --nodes <node_name_1> <node_name_2> <label_name>=<label_value>

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

# Manejo de clusters con Minikube y Kubectl

En esta seccion se explica como crear, eliminar, iniciar y detener clusters de Kubernetes usando Minikube y Kubectl.

> [!WARNING]
>
> Minikube y Kubectl usan contextos distintos, por lo general minikube puede cambiar su propio contexto y el de kubectl pero es necesario que este pendiende de que esta usando el mismo contexto en ambos para no causar conflictos ni daños en sus cluster.

> [!NOTE]
>
> **TIP 1**
>
> - Puede usar el comando "minikube profile list" para comparar, "Active Profile" es el contexto que usa minikube y "Active Kubecontext" es el contexto que usa kubectl.
> - Puede usar el comando "kubectl config get-contexts" para ver el contexto que usa únicamente kubectl.

> [!TIP]
>
> **TIP 2**
>
> Para este tutorial entiendase "contexto", "perfil" y "cluster" como sinónimos que se refieren a lo mismo.

## Comandos de perfiles (clusters) en minikube

### Listar perfiles (clusters)

> minikube profile list

### Activar/Usar perfil (cluster)

Esta opción hace que minikube use el perfil indicado pero no necesariamente lo inicia.

> minikube profile <profile_name>

### Iniciar perfil (cluster)

Esta opción es para correr los nodos del perfil, si no existe un perfil con ese nombre se crea uno nuevo.

> minikube start --profile <profile_name>

### Detener perfil (cluster)

> minikube stop --profile <profile_name>

### Eliminar perfil (cluster)

> minikube delete --profile <profile_name>

## Comandos de contexto (clusters) en kubectl

### Listar contextos (clusters)

> kubectl config get-contexts

### Activar/Usar contexto (cluster)

> kubectl config use-context <context_name>

## Fuente de la primera parte (práctica de 3 nodos)

Para la parte práctica se ha seguido el [articulo de Medium](https://medium.com/womenintechnology/create-a-3-node-kubernetes-cluster-with-minikube-8e3dc57d6df2)
