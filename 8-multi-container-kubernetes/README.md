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