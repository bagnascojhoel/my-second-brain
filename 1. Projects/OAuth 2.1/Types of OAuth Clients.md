- **Confidential**: if the application can be deployed with credentials, securely. Basically, it must run on a private and controlled hardware.
- **Public**: if the application doesn't have the ability to hold credentials in a secure manner. When the application runs on a machine, the user controls. 
- **Credentialed**:

With this distinction of clients, it's possible to have different policies for each type of client. Example: for confidential clients, you may want to remove a User Consent screen, as to improve UX. You can do that with an ease mind because you'll know it is your known client making the request. However, for public clients, you can never know who is making the request. An attacker may easily find out the client's name and, since a client secret is not usable, pass as the client. The Authorization Server will have no way of knowing that it is not the application making the request. To minimize that breach, you may want to enable the user consent screen, getting the user involved in what is happening.

---
- If the App is running on a machine the user controls, there is currently no way to ship with credentials securely. That is the case for Mobile, SAP, Smart TV's, IOT devices, ...