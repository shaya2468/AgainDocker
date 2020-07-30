![Screen Shot 2020-07-22 at 17 55 10](https://user-images.githubusercontent.com/8313826/88191823-86d26800-cc44-11ea-96dd-5423fffbe171.png)

- we will have a config file fore every item

![Screen Shot 2020-07-22 at 17 57 57](https://user-images.githubusercontent.com/8313826/88192172-e4ff4b00-cc44-11ea-8a8c-e823a5393833.png)

![Screen Shot 2020-07-22 at 18 07 03](https://user-images.githubusercontent.com/8313826/88193292-2cd2a200-cc46-11ea-8d68-540be8fa24ab.png)

![Screen Shot 2020-07-22 at 18 26 41](https://user-images.githubusercontent.com/8313826/88195679-f8acb080-cc48-11ea-9043-6f9d393aee24.png)


- to apply a group
```k apply -f <name of folder>```
- to see all is good
```k get deployments```
```k get pods```

- the worker doesn't need a port assigned to it cuz no1 should be able to access it

![Screen Shot 2020-07-23 at 9 07 57](https://user-images.githubusercontent.com/8313826/88256447-06ebe280-ccc4-11ea-8040-6ad35c7bd899.png)

## Volumes
 - We need to seperate between the postress pod, and where the data is stored, this problem introduces VOLUMES.
 - Kubernetes volumes is not like docker volumes and there are some distinctions
 - Volume lives with a pod, when the pod dies it dies with it. it lives over container crashes, not pod crashes
 - Persistent Volume is not tied to any specific pod
 
## Persistent volume claim
- It lists the storage options(500gb , 1 tb) and you assign it to a pod
- statically provisioned - A volume that is created ahead of time
- dynamically provisioned - A volume that is created on the fly

![Screen Shot 2020-07-23 at 9 48 07](https://user-images.githubusercontent.com/8313826/88258891-db6bf680-ccc9-11ea-8f25-067b34255c4b.png)

- ```k get pvc``` all the persitent volumes CLAIMS - "you can get this thing if you want to, advertisement"
- ```k get pv``` all the persitent volumes - "an actual instance of the claim"
 
## Secrets
- Securely store a piece of information in the cluster, such as a database password
- you can't use a config file because that defeats the purpose, so we use the imperative approuch.
![image](https://user-images.githubusercontent.com/8313826/88887308-d1577400-d244-11ea-86d8-1369787c2619.png)

- type of secret is generic. there are 2 others, docker-registry and the other is tls is for http setup. in our case we arne' using a docker registry just docker hub.
```k create secret generic pgpassword --from-literal PGPASSWORD=123abc```
```k get secrets```

## Ingress

- we could use our own nginx but were using ingress-nginx because it's suited for kubernetes

- Optional reading about ingress nginx - https://www.joyfulbikeshedding.com/blog/2018-03-26-studying-the-kubernetes-ingress-system.html

- installation guide here - https://kubernetes.github.io/ingress-nginx/deploy/

```kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v0.34.1/deploy/static/provider/cloud/deploy.yaml```

```kubectl get pods -n ingress-nginx```

- When we do it for google, we'll do what it says on the website for GKE

![image](https://user-images.githubusercontent.com/8313826/88895170-619bb600-d251-11ea-8308-f9b6ce8f39a7.png)

![image](https://user-images.githubusercontent.com/8313826/88896001-e8509300-d251-11ea-86f3-05fab8b353ce.png)

- we are going to implement this rule set:

![image](https://user-images.githubusercontent.com/8313826/88897834-9b21f080-d254-11ea-9d52-d6ea69298ec7.png)

- "Creating the ingress configuration" : important lesson that shows the ingress-service.yaml for locally

