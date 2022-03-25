# DAO vs Repository
The definition of each concept ends up being equal in many contexts. Even so, they do have some differences ([this StackOverflow post shows exactly how confusing it can be when trying to understand their use cases](https://stackoverflow.com/questions/8550124/what-is-the-difference-between-dao-and-repository-patterns)). Before going into the differences, we should listen their similarities:
- both are DAL (Data Access Layer);
- both don't care about how data is stored.

### Repository
Repository is a **collection of objects**. It should be able to do everything a collection can, like add a new item, delete a specific registry, fetch all objects for a given filter. It does not care how the data is structured.
There are two main approached to repositories:
- Persistency-oriented, where you define methods in a persistency-like manner (e.g. `customerRepository.save()`), or
- Collection-oriented, where your methods created as if for an in-memory array (e.g. `customerRepostiory.add(object)`).

Although some people arguee that this next distinction can also be applied to DAO's, it is commonly treated as a feature specific to Repositories. The distiction I mean is that Repositories are *domain-oriented*. 
Let's say my application uses a relational database. This database has two tables `customer` and `customer_address`. The `customerRepository.save(customer)` will create records on both tables.

![[Pasted image 20220325171500.png]]

### DAO (Data Access Object)
It is an abstraction layer built around **a single object**.

![[Pasted image 20220325171157.png]]

## Sources
- [What is the difference between DAO and Repository patterns?](https://stackoverflow.com/a/14967950/13158496)
- [Think to code, Repository Pattern](https://www.thinktocode.com/2018/01/08/repository-pattern/)
- 