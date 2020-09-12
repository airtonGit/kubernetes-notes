## Kubernetes K8s dicas rapidas
Consulta rápida para o dia que o Google não funcionar :D

**Kubernetes vs Docker**

|info| swarm | kubernetes|
|----|-------|-----------|
|listar 'serviços'| ```docker service list``` | ```kubectl get pods``` |
|logs do serviço/container| ```docker service logs service-name``` | ```kubectl logs deployment-name container-name``` |
|executar comando dentro do container| ```docker exec -it container-id command``` | ```kubectl exec -it pod-name [-c container-name] -- /path/command ``` |
|listar containers em pod/serviço |   | ```kubectl describe pod/srv pod-name/srv-name``` |
|mapeamento de porta||```kubectl port-forward POD_NAME 3306:3306 --address 0.0.0.0```|

## Ferramentas de Log

⎈ Multi pod and container log tailing for Kubernetes [https://github.com/wercker/stern](https://github.com/wercker/stern)

## Debuging

**containers in pod:**

```kubectl describe pod/name-deployment-8997fb557-jl68z -n default```

**Listar status**

```kubectl describe pods```


## Executar BASH dentro do container

```kubectl exec -it nome-deployment -c nome-container -- /bin/bash```

## Configuração

**Expor Cluster para Internet**

  * Configurar Service com NodePort https://kubernetes.io/docs/concepts/services-networking/service/#nodeport
  
## Ports

+ Port exposes the Kubernetes service on the specified port within the cluster. Other pods within the cluster can communicate with this server on the specified port.

+ TargetPort is the port on which the service will send requests to, that your pod will be listening on. Your application in the container will need to be listening on this port also.

+ NodePort exposes a service externally to the cluster by means of the target nodes IP address and the NodePort. NodePort is the default setting if the port field is not specified.

