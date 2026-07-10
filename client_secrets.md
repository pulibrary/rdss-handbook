# RDSS Best Practice for Managing Client Secrets

## What is a client secret?
A client secret is a confidential credential used in OAuth 2.0 and similar authentication/authorization flows to verify the identity of an application (the "client") when it communicates with an authorization server or API.

For PUL we will be using Client Secrets in production for [EntraID](https://github.com/pulibrary/pul-it-handbook/blob/main/services/entra-id.md). Some of the documentation for EntraID says not to do this and instead to use certificates. We know that but our Operations team have suggested to use Client Secrets, at least for now. 

We do have a way of rotating client secrets to mitigate the issue in the event the secret gets leaked. 

* Client ID — a public identifier for the app, similar to a username. It's not secret and can be exposed in code or URLs (your app's username).

* Client secret — a private string, similar to a password, that only the application (and the authorization server) should know (your app's password).

## Why do they matter?

Client secrets stops random people or malicious software from pretending to be your application.

* They protect access to data and systems.
* They enable trust between systems without a human involved.

## Where should the client secrets be stored?

Secrets should be rotated periodically and stored in secure vaults.

TODO: Document what Carolyn has already set up

## What happens if a client secret get leaked?

If a client secret leaks, anyone with it can potentially authenticate as your application until it's revoked or rotated.

### To revoke or rotate a token:
* Login to EntraID and delete the client secret that already exists to invalidate it
* Create a new client secret and store it in lastpass and ansible vaults for ORCID
* Run the playbook to update the app_vars on the servers that the key was leaked

## How do we register one for EntraID?

Documentation here at step 5: https://github.com/pulibrary/pul-it-handbook/blob/main/services/entra-id.md

## What are the procedures for if a team member leaves or joins

### When someone joins
1. Identity & account setup
    * Create their Entra ID account 
    * Assign to the correct security groups and Microsoft 365 groups based on role 
    * Enable MFA from day one
2. App & resource access
    * Add them to relevant shared mailboxes
3. Documentation
    * Log the access granted (date, groups, apps) — useful for audits and for offboarding later
### When someone leaves
1. Immediate access revocation (same day, ideally same hour)
    * Disable their Entra ID account
    * Revoke active sessions/tokens (Entra ID → Users → [user] → Revoke sessions) — this is important because just disabling the account doesn't always kill existing active tokens immediately
    * Remove from all security groups and Microsoft 365 groups
