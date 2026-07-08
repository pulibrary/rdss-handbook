# RDSS Best Practice for Managing Client Secrets

## What is a client secret?
A client secret is a confidential credential used in OAuth 2.0 and similar authentication/authorization flows to verify the identity of an application (the "client") when it communicates with an authorization server or API.

Sometimes called an application password, a client secret is a string value your app can use in place of a certificate to identify itself.

Client secrets are less secure than certificate or federated credentials and therefore should not be used in production environments. While they may be convenient for local app development, it's imperative to use certificate or federated credentials for any applications running in production to ensure higher security

* Client ID — a public identifier for the app, similar to a username. It's not secret and can be exposed in code or URLs (your app's username).

* Client secret — a private string, similar to a password, that only the application (and the authorization server) should know (your app's password).

## Why do they matter?

Client secrets stops random people or malicious software from pretending to be your application.

* They protect access to data and systems.
* They enable trust between systems without a human involved.

## Where should the client secrets be stored?

Secrets should be rotated periodically and stored in secure vaults (e.g., Azure Key Vault, AWS Secrets Manager or whatever you secure vault you feel comfortable with) rather than hardcoded or committed to source control. 

## What happens if a client secret get leaked?

If a client secret leaks, anyone with it can potentially authenticate as your application until it's revoked/rotated.

## How do we register one for EntraID?

1. In the Microsoft Entra admin center, in App registrations, select your application.

2. Select Certificates & secrets > Client secrets > New client secret.

3. Add a description for your client secret.

4. Select an expiration for the secret or specify a custom lifetime.

    * Client secret lifetime is limited to two years (24 months) or less. You can't specify a custom lifetime longer than 24 months.
    * Microsoft recommends that you set an expiration value of less than 12 months.

5. Select Add.

6. Record the client secret Value for use in your client application code. This secret value is never displayed again after you leave this page.

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