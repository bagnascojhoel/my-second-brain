These are **roles**, not distinct components. Meaning that a architectural component may have one or more roles (e.g. an API which has)
- **Resource Owner** or User
- **User Agent** or Device
- **OAuth Client** or Application: an web or mobile App. The software that is going to access data from the Resource Server.
- **Resource Server** or API: the application which holds data.
- **Authorization Server**
---
- The User only inputs their password into the Authorization Server. Neither the Resource Server nor the OAuth Client will have access to the User's input. 