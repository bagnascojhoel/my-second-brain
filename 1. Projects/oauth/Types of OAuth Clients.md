- **Confidential**: this client has credentials and the Authorization Server always trusts that it is the specific client.
	- Should be used if the application can be deployed with credentials securely. Basically, it must run on a private and controlled hardware. 
	- Ensures that only known clients issue access tokens.
- **Credentialed**: this client has credentials and the Authorization Server knows the specific client after a handshake.
	- The OAuth Client uses dinamic client registration to request a client-secret. The Authorization Server issues the client-secret. The client may then send the client-secret in the following requests. That way, the communication after the handshake in secure. (Note that an attacker will have a hard time intercepting an access token issues for a Credentialed client, but it may register itself as a client.)
	- Ensures that refresh tokens are always redeemed by the same client. But not that only known clients attempt authentication.
- **Public**: this client has no credentials and the Authorization Server never knows if it is a specific client making the request or an attacker.
	- Should be used if the application doesn't have the ability to hold credentials in a secure manner. When the application runs on a machine that user controls.  

With this distinction of clients, it's possible to have different policies for each type of client. Example: for confidential clients, you may want to remove a User Consent screen, as to improve UX. You can do that with an ease mind because you'll know it is your known client making the request. However, for public clients, you can never know who is making the request. An attacker may easily find out the client's name and, since a client secret is not usable, pass as the client. The Authorization Server will have no way of knowing that it is not the application making the request. To minimize that breach, you may want to enable the user consent screen, getting the user involved in what is happening.

---
- If the App is running on a machine the user controls, there is currently no way to ship with credentials securely. That is the case for Mobile, SAP, Smart TV's, IOT devices, ...