# DAO vs Repository
The definition of each concept ends up being equal in many contexts. So their differences can be hard to understand ([this StackOverflow post shows exactly how confusing it is](https://stackoverflow.com/questions/8550124/what-is-the-difference-between-dao-and-repository-patterns)).
### DAO (Data Access Object)
It is an abstraction layer built around **database tables**.

![[Pasted image 20220325171157.png]]

### Repository
It is a layer of abstraction that encapsulates storage, retrieval and search of a **collection of objects**.

![[Pasted image 20220325171500.png]]
```ad-note
title: DAO vs Repository

DAO is a interface of the persistency mechanism for an object. On the other hand, a Repository is an interface for everything related to storage, retrieval and search of 
```

