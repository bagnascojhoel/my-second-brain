# Liquibase
An application that uses a database to persist some data, has to ensure every change is known and ran for every database it connects to. Otherwise, your databases will start to be incosistent.
Let's say you are developing a blog. Your blog allows people to create accounts to publish their own posts or interact with other users' posts. To make sure no one ends up accessing a collum that does not exists, you decide to use a schema.
The blog is already published. So your database already has (hopefully) many records on a `post`s table (or whatever name your no-relational databases uses). A `post` needs to be linked to a `user`. The current `post` table uses a field named `federated_user_id` which relates to an authentication made through a social provider like Google, Apple and GitHub. Time passed and now you decided to remove social login from your application. You don't want to lose all posts created by users who used a social login. 

A local database may have a table `user` with properties `first_name` and `last_name`,   
![[Pasted image 20220326103824.png]]
## Best Practices


### Sources
- [Some best practices to keep in mind when using Liquibase](https://liquibase.org/get-started/best-practices)