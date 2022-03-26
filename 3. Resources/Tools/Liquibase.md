# Liquibase
An application that uses a database to persist some data, has to ensure every change is known and ran for every database it connects to. Otherwise, your databases will start to be incosistent.
Let's say you are developing a blog. Your blog allows people to create accounts to publish their own posts or interact with other users' posts. The blog is already running on a AWS EC2 instance and 
A local database may have a table `user` with properties `first_name` and `last_name`,   
![[Pasted image 20220326103824.png]]
## Best Practices


### Sources
- [Some best practices to keep in mind when using Liquibase](https://liquibase.org/get-started/best-practices)