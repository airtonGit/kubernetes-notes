## Kubernetes K8s dicas e manhas
Consulta rápida para o dia que o Google não funcionar :D

**Kubernetes vs Docker**

| swarm | kubernetes|
|-------|-----------|
| ```docker service list``` | ```kubectl get pods``` |
| ```docker service logs service-name``` | ```kubectl logs deployment-name container-name``` |
| ```docker exec -it container-id command``` | ```kubectl exec -it pod-name [-c container-name] -- /path/command ``` |
|   | ```kubectl describe pod/srv pod-name/srv-name``` |

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
