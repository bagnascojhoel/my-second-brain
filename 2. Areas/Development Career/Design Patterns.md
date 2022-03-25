# DAO vs Repository
The definition of each concept ends up being equal in many contexts. Even so, they do have some differences ([this StackOverflow post shows exactly how confusing it can be when trying to understand their use cases](https://stackoverflow.com/questions/8550124/what-is-the-difference-between-dao-and-repository-patterns)). Before going into the differences, we should listen their similarities:
- both are DAL (Data Access Layer);
- both don't care about how data is stored.

### DAO (Data Access Object)
It is an abstraction layer built around **a single object**.

![[Pasted image 20220325171157.png]]

### Repository
Repository is a **collection of objects**. It should be able to everything a collection can, like add a new item, delete a specific registry, fetch all objects in a given filter. It does not care how the data is structured.

![[Pasted image 20220325171500.png]]
```ad-note
title: DAO vs Repository

DAO is a interface of the persistency mechanism for an object. On the other hand, a Repository is an interface for everything related to storage, retrieval and search of 
```

## Sources
- https://stackoverflow.com/a/14967950/13158496
- https://www.thinktocode.com/2018/01/08/repository-pattern/