# User Consent
## App's should never know your password
 The user's password should never be shared with an OAuth Client. If the client ever gets their hands of the user's password, it could pass as if they were the user. The solution for this is the presence of the Authorization Server. This way, the password is always inputted in a secure environment. And with a user consent screen, the Authorization Server knows that the user is actually trying to authenticate.

## You must know what information they are receiving
If the OAuth Client needs some information about the user, they must request them from the Authorization Server. The server will then display the information the App will be receiving on the user consent screen. That way you will always know what the App uses.

## There are some who can be trusted
Although the user consent step adds important security mechanisms, it still interrupts the flow and can damage user experience. Normally it would be strongly recommended to enable a user consent step, but for these cases the experience can be improved without any security weakening:
- **First-party App's**
	- E.g. Gmail asks you to sing-in with Google
	- If an App owned by the same owner of the Authentication Server requests authentication, the user consent screen is redundant. If the App wanted to do something bad, it wouldn't need to ask the user for data, since it already has it.
- **Confidential Client**
	- A confidential client should be trust-worthy. Since they have secrets (assuming they handle it properly), the Authorization Server can be sure that they are who they say.

(If you are still worried that attackers may trick your user's into sharing their data, you can still enable the user consent step. Making life even harder for the attacker.)