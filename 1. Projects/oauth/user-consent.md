# User Consent
## App's should never know your password
 The user's password should never be shared with an OAuth Client. If the client ever gets their hands of the user's password, it could pass as if they were the user. The solution for this is the presence of the Authorization Server. This way, the password is always inputted in a secure environment. And with a user consent screen, the Authorization Server knows that the user is actually trying to authenticate.

## You must know what information they are receiving
If the OAuth Client needs some information about the user, they must request them from the Authorization Server. The server will then display the information the App will be receiving on the user consent screen. That way you will always know what the App uses.

## There are some who can be trusted
The user consent step interrupts the flow and can be 