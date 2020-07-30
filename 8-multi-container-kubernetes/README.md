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
 
 