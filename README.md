# Práctica de Minikube con 3 nodos

Este es un repositorio de práctica para crear un cluster de Kubernetes con 3 nodos usando minikube.

## Comandos utiles

### Crear cluster de # nodos llamado <cluster_name>

    minikube start --nodes # --profile <cluster_name>

- **--profile** ó **-p**: Sirve para establecer el nombre que se le dará al cluster (en minikube se conoce como perfil)

### Asignar label a los nodos

    minikube label --nodes <node_name_1> <node_name_2> <label_name>=<label_value>

### Ejecutar deployment en kubernetes

    kubectl apply -f <deployment.yaml>

### Obtener información básica de un pod

Obtener la informacion de READY, STATUS, RESTARTS, AGE

    kubectl get pod <pod_name>

### Obtener información detallada de un pod

Obtener la informacion básica + IP, NODE, NOMINATED NODE, READINESS GATES

    kubectl get pod <pod_name> -o wide

## Comandos de limpieza

### Eliminar deployments

    kubectl delete deployments <deployment_name> <deployment_name>

### Eliminar nodos de cluster desde kubectl

    kubectl delete nodes <node_name> <node_name>

### Detener minikube

    minikube stop

### Eliminar cluster de minikube

    minikube delete

<hr>

# Manejo de clusters con Minikube y Kubectl

En esta seccion se explica como crear, eliminar, iniciar y detener clusters de Kubernetes usando Minikube y Kubectl.

> [!WARNING]
>
> Minikube y kubectl manejan contextos diferentes. Aunque Minikube puede cambiar tanto su propio contexto como el de kubectl, es crucial revisar manualmente que cluster se está usando en cada caso para evitar conflictos, daños o mofidicaciones no deseadas.

- Puede usar el comando siguiente comando para revisar los contextos que usa Minikube y Kubectl:

      minikube profile list

  - **Active Profile** es el contexto que esta usando minikube.
  - **Active Kubecontext** es el contexto que esta usando kubectl.

- Puede usar el comando el siguiente comando para ver que contexto se esta usando actualmente en kubectl:

        kubectl config get-contexts

> [!TIP]
>
> Para este tutorial entiendase "contexto", "perfil" y "cluster" como sinónimos que se refieren a lo mismo.

## Comandos de perfiles (clusters) en minikube

### Listar perfiles (clusters)

    minikube profile list

### Activar/Usar perfil (cluster)

Esta opción hace que minikube use el perfil indicado pero no necesariamente lo inicia.

    minikube profile <profile_name>

### Iniciar perfil (cluster)

Esta opción es para correr los nodos del perfil, si no existe un perfil con ese nombre se crea uno nuevo.

    minikube start --profile <profile_name>

### Detener perfil (cluster)

    minikube stop --profile <profile_name>

### Eliminar perfil (cluster)

    minikube delete --profile <profile_name>

## Comandos de contexto (clusters) en kubectl

### Listar contextos (clusters)

    kubectl config get-contexts

### Activar/Usar contexto (cluster)

    kubectl config use-context <context_name>

<hr>

## Fuente de la primera parte (práctica de 3 nodos)

Para la parte práctica se ha seguido el [articulo de Medium](https://medium.com/womenintechnology/create-a-3-node-kubernetes-cluster-with-minikube-8e3dc57d6df2)
