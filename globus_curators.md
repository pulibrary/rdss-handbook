# Globus for Curators

We give special access to our curators to our Globus collections so that they can help researchers with large deposits.

When a curator needs to deposit files to our Princeton Data Common Collections in Globus  we need to create AWS IAM keys for them and add them as administrators to the Collection in Globus.

## Creating AWS IAM Keys for Curators
1. Visit princeton.edu/aws and log in
1. Click on the IAM User services
1. Click on the Users on the left hand side
1. Click Add User in the top right
1. Fill in User Name with `pdc-<netid>`
1. Click `Next`
1. Choose `pdc-curator` as the group
1. Click `Next`
1. Fill in `RDOS` & `PDC` as tags
1. Click `Create User`
1. find your new user `pdc-<netid>` and click on the name
1. Click on `Security Credentail` tab
1. Click `Create Access Key`
1. Choose `Application running outside AWS`
1. Click `Next`
1. Show Private key and copy contents
1. On a new browser tab, Add an SSH Key to LastPasss
1. Fill in Private Key
1. Grab Public key from AWS tab
1. On LastPass tab fill in private key and name the entry `PDC Globus <curator name> Curator Key`
1. On LastPass tab go to sharing center at the bottom
1. Click the Red Plus to add a shared folder
1. Name it PDC-Globus-<curator-name>
1. Click on Create
1. Click on Manage when hovering over the new Folder
1. Add the curator as an Administrator
1. Click Invite
1. Click Save
1. Contact the Curator to let them know about the key

## Adding a new administrator to a collection in Globus
1. Login as rdss-globus in an incognito window (see lastpass "rdss globus service account" for login credentials)
1. Invite the curator to the "PRINCETON CURATORS" group
    1. click on groups
    1. click on "PRINCETON CURATORS"
    1. click on "Invite Other"
    1. use the Curators email to find them 
    1. Choose Member access

