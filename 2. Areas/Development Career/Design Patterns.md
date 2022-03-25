# DAO vs Repository
The definition of each concept ends up being equal in many contexts. Even so, they do have some differences ([this StackOverflow post shows exactly how confusing it can be when trying to understand their use cases](https://stackoverflow.com/questions/8550124/what-is-the-difference-between-dao-and-repository-patterns)).
- They both are DAL (Data Access Layer).

### DAO (Data Access Object)
It is an abstraction layer built around **a single **.

![[Pasted image 20220325171157.png]]

### Repository
It is a layer of abstraction that encapsulates storage, retrieval and search of a **collection of objects**.

![[Pasted image 20220325171500.png]]
```ad-note
title: DAO vs Repository

DAO is a interface of the persistency mechanism for an object. On the other hand, a Repository is an interface for everything related to storage, retrieval and search of 
```

## Sources
- https://stackoverflow.com/a/14967950/13158496