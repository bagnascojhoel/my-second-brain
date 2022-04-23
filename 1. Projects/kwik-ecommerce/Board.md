---

kanban-plugin: basic

---

## Todo

- [ ] Implement e-mail authentication flow<br>---<br>- [ ] Create endpoint to request authentication<br>  - Client sends an e-mail and always receives an *Accepted* HTTP status.<br>  - If the e-mail exists as a user, the backend sends an e-mail to it. If not, it logs the attempt.<br>  - The e-mail sent should contain a random token. This token will then be used to authenticate.<br>- [ ] Create endpoint to authenticate<br>  - Client sends the received token.<br>  - If the token matches the expected one, the backend should generate an access token, a refresh token and an expiration date for each of those tokens.


## Done





%% kanban:settings
```
{"kanban-plugin":"basic"}
```
%%