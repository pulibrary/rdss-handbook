# Globus

[Globus](https://www.globus.org/data-transfer) is a fast, reliable file transfer service that makes it easy for users to move data between two GridFTP servers or between a GridFTP server and a user's machine (Windows, Mac or Linux). It is increasingly used by researchers to transfer large data sets because it provides faster and more reliable transfers than previous methods.

For a quick intro to Globus take a look at [Globus for newbies](https://docs.google.com/document/d/1d8u3KhsoX-x3k59GgWfhC7325R6616j8RytccTelPWM/edit#).

Our globus setup consists of four globus collections connected to two s3 buckets on two globus endpoints.

```mermaid
  graph TD;
      S31["Precuration S3 (private) [pdc-describe-*-precuration]"]-->SG1
      S32["Precuration S3 (private)  [pdc-describe-*-precuration]"]-->SG2
      subgraph "Precuration EC2 []]"
         subgraph "PreCuration Globus Endpoint []]"
         SG1["Precuration Storage Gateway []"]-->B["Pre Curated Collection (private) []"]
         SG1-->F["Pre Curated Guest Collection (public read/write) []"];
         end
      end
      subgraph "Postcuration EC2 []]"
      subgraph "Postcuration Globus Endpoint []]"
      SG2["Post Curation Storage Gateway []"]-->D["Curation Collection(curator only read/write) []"];
      SG2-->E["Public Guest Globus Collection (public read) []"];
      end
      end
```
**TODO: What are the real names in our new setup**

## Current Globus Setup

There are currently two EC2 Servers serving up the exact samne globus structure.  Need to find out why that is...
Current Globus collections for dataspace
#### Endpoint
  There is a single globus enpoint: `Princeton Data Repository Endpoint`
#### Storage gateways
  There are currently four storage gateways:
  * Princeton DSS Gateway - S3 Gateway `dss-server-data3` (defunct)
  * Princeton Dataspace Posix Gateway  - POSIX Gateway - ??? (defunct)
  * Princeton Dataspace s3 Gateway - S3 Gateway `prds-globus`
  * Princeton Research Data Dataspace Gateway - S3 Gateway `prds-dataspace`
#### Collections
  There are currently six collections:
  * another_test                                               | fkayiwa@princeton.edu | guest           | Princeton Research Data Dataspace Gateway
  * Princeton University Library Data and Statistical Services | fkayiwa@princeton.edu | mapped          | Princeton DSS Gateway
  * Princeton Dataspace Collection                             | fkayiwa@princeton.edu | mapped          | Princeton Research Data Dataspace Gateway
  * Princeton Dataspace Posix Collection                       | fkayiwa@princeton.edu | mapped          | Princeton Dataspace Posix Gateway
  * Princeton Research Data Repository                         | mjc12@princeton.edu   | guest           | Princeton Research Data Dataspace Gateway
  * CG                                                         | fkayiwa@princeton.edu | guest           | Princeton Research Data Dataspace Gateway
  
  **Note:** There seem to be collections for PDC, DSS, Dataspace and the POSIX collection.  We should figure out what these collections are all for...

## New Globus Setup
  * There should be one or two globus endpoints for each environment (staging & prod)
    * staging
    * prod
  * They should exist on (one or two separate) EC2 instances
    * staging
    * prod
  * They will connect with two s3 buckets
    * staging
      * pdc-describe-staging-precuration
      * pdc-describe-staging-postcuration
    * prod
      * pdc-describe-prod-precuration
      * pdc-describe-prod-postcuration
  * Each bucket will have a storage gateway attached in the correct globus endpoint
  * Each storage gateway will have a mapped collection and a guest collection attached in the correct globus endpoint


## Account setup
In order to help maintain our Globus infrastructure you'll need an AWS account with the right permission. See the [onboarding](onboarding.md) documentation for how to set that up.

## Prequisites
  * To build an ami please install the prequisites from https://github.com/pulibrary/vm-builds#prerequisite-software
    * The following steps require awscli which should be installed as part of vm-builds
  * You will be utilizing [princeton-ansible](https://github.com/pulibrary/princeton_ansible#macos).  Please make sure the environment is set up on your local machine

## Data management
### pre-curation

### post-curation
Our Globus instance is for research data that has gone through curation. Because 
it has gone through curation, it will always have a [DOI](https://www.doi.org/), and it is organized under its DOI number. 

Data is stored in S3 buckets. We are in the process of building a new Globus production system. (Project plan [here](https://docs.google.com/document/d/13HkbOoC7OLD70FIEwFlHs8zi2Z8h53Puflm7DCcjnSw/edit).)

Our legacy Globus instance has its data in an S3 bucket called `prds-dataspace`.
Our new PDC branded globus instance will have its data in a bucket called `pdc-globus-prod`.

## Gonfiguraing Globus
### Making a new S3 bucket
To make a new S3 bucket with a copy of the PDC Globus data:
1. To access the aws console first got to https://princeton.edu/aws and log in
1. Then access https://s3.console.aws.amazon.com/s3/buckets?region=us-east-1# for the s3 buckets
1. Click create new bucket
1. Name the bucket
1. Under `Copy settings from existing bucket` choose `prds-dataspace` 
1. Under `Object Ownership` choose enable ACLs
1. uncheck `Block all public access` and acknowlegde `Turning off block all public access might result in this bucket ...`
1. click `Save`
1. (Optionally) Copy the data using the aws cli: `aws s3 sync s3://prds-dataspace s3://pdc-globus-prod`

    **Note:** that this will take about five hours. 

### Creating the service account (Not needed each time)
  1. Fillin the ticket in [service now](https://princeton.service-now.com/service?id=sc_cat_item&sys_id=f44539ab4ff81640f56c0ad14210c77c)
      * Duration: Permanent
      * Type: General
      * Service Account User(s): Team members should be added here

   1. after the account is set up a password must be selected and stored in lastpass

   1. Duo will be enabled and the first person to enable it will always get extraneous duo (Just ignore duo for the service account unless asked)
   1. Other folks will follow https://princeton.service-now.com/service?id=kb_article&sys_id=575eff5387064dd012ae43bd0ebb35b0#section5 to add their device to duo.  Make sure to name the device with your name.

### Creating the ami (Not needed each time)

 1. run `packer build aws-globus.pkr.hcl` from the [vm-buids](https://github.com/pulibrary/vm-builds) directory on your local machine
 1. see your new ami in [AWS](https://us-east-1.console.aws.amazon.com/ec2/v2/home?region=us-east-1#Images:visibility=owned-by-me)

### Creating the AWS EC2 instance from AMI

1. In princeton-ansible check the group_vars/globus/common.yml to make sure the image_id matches the ami you either created or are using
1. Run the playbook with either staging (default) or production (`-e runtime_env=production`).  For example the command below will create a staging EC2 instance named  pdc-globus-staging 
   ```
   ansible-playbook playbooks/aws_ec2.yml -e ec2_name=pdc-globus-staging-precuration
   ```

1. See your new instance in [AWS](https://us-east-1.console.aws.amazon.com/ec2/v2/home?region=us-east-1#Instances:instanceState=running)  Note the IP address you will need it to configure Globus in following steps


### Configure Globus Connect Server
To register a Globus Endpoint do the following:
1. Go to [developers.globus.org](https://developers.globus.org), sign in   
2. Add a new Globus Connect Server and fill 2out the form in the **Princeton Data Commmons Production** or **Princeton Data Commmons Staging** Projects. 
   1. Type in the new name
   1. click Register Globus Connect Server 
3. Generate a client secret.  Be ready to save the value off, you will only see it once.
   1. Click Generate a New Client Secret within the new section on the website created by the step above
   1. Fill in the description of the secret (can be anything)
   1. Click Save
   1. **Save the Client ID and Client Secret values in a note in "Shared-ITMS-Passwords" in Lastpass** (They are needed in the next step) 
4. Log into the virtual machine and configure globus:
   1. `ssh pulsys@<public IP>`
   1. Once on the server run
      ```bash
      mkdir app_config
      cd app_config
      globus-connect-server endpoint setup "Princeton Data Commons Globus Staging"  --organization "Princeton University Library" --client-id "<your client id>" --owner rdssglobus@princeton.edu --contact-email lsupport@princeton.edu
      ```
         1. you will be prompted for the client secret
         1. Accept Let's Encrypt ToS
         1. It will then run for some time (10 minutes about) and then give you a URL to paste into a browser
         You will get a response close to this

            ```bash
            Please authenticate with Globus to set the owner of the endpoint:
            ----------------------------------------------------------------
            https://auth.globus.org/v2/oauth2/authorize?client_id=auuid-&redirect_uri=https%3A%2F%2Fauth.globus.org%2Fv2%2Fweb%2Fauth-code&scope=urn%3Aglobus%3Aauth%3Ascope%3Atransfer.api.globus.org%3Aall&state=_default&response_type=code&access_type=online&session_required_identities=uuid&session_message=Set+the+advertised+owner+of+the+endpoint
            ----------------------------------------------------------------
            ```
        1. Paste the results from your browser to complete endpoint creation.

         1. click on the link rddglobus@princeton.edu on the page and it will create a code
         1. paste the above code in on the command line
         1. It will then finish giving you a url for google cloud storage
         1. This will also create a `deployment-key.json` file in the `app_config` directory. This is an important file that 

## Configure Globus Node
Still in your VM in the `app_config` directory run the following command to configure your node: (note: use of `sudo`)

```bash
sudo globus-connect-server node setup \
    --client-id "your client id"
sudo systemctl restart apache2
```
Finish the setup by running this on the VM

```bash
sudo globus-connect-server login localhost
```

### Register the Endpoint with OIT
   **This ia a manual step.**

   1. ssh onto the EC2 instance `ssh pulsys@<public IP>`
   1. run `sudo globus-connect-server endpoint show`
   1. email `tengi@princeton.edu` with subject `Register Globus Endpoint`

      ```
      Hello Chris,

      Can you please register the following Princeton Research Data Globus endpoint to be managed by Research Computing's Globus account:

      <copy and paste from step 1>
      We will be connecting this endpoint to an S3 bucket.

      Thank you!

      -- <your name>
         Princeton University Library

      ```

### Register all admin users on the endpoint
      1. go to https://app.globus.org/console/endpoints signed in as rdssglobus (see last pass)
      1.  click on New endpoint and Continue for Authentication Consent
      1. Add administrators via the command line
         ```
         sudo globus-connect-server endpoint role create administrator rdssglobus@princeton.edu
         sudo globus-connect-server endpoint role create administrator cac9@princeton.edu
         sudo globus-connect-server endpoint role create administrator fkayiwa@princeton.edu
         sudo globus-connect-server endpoint role create administrator bs3097@princeton.edu
         sudo globus-connect-server endpoint role create administrator hc8719@princeton.edu
         sudo globus-connect-server endpoint role create administrator jrg5@princeton.edu
         sudo globus-connect-server endpoint role create administrator kl37@princeton.edu
         ```


### Connect globus endpoint to S3 bucket

      1. login to globus
         `sudo globus-connect-server login localhost`
          * paste the url in to your browser
         **NOTE:** Depending on the browser you paste the url into, you will be logged in as that person.  If you put it into an incognito and login with rdssglobus you will be rdssglobus.  If you use a browser that you are logged into then you will be logged into the connect server as yourself.  If you receive messages like `None of your identities have been granted a role to access this resource` you may need to get administrator access for your account, or login as rdssglobus instead. 


      1. Add the S3 bucket as 
         ```
         sudo globus-connect-server storage-gateway create s3     "S3 Storage Gateway"     --domain princeton.edu     --s3-endpoint https://s3.amazonaws.com --s3-unauthenticated    --bucket pdc-globus-staging-precuration
         ```
         **Note** the id returned by this command, you will need it in the following

       1. Assign the gateway id to a variable
          ```
          export gateway_id=<output from above command>
          ```

### Create a mapped Collection for access to the S3 bucket
   1. Create a collection for the bucket
         ```
         sudo globus-connect-server collection create $gateway_id / "Library Pre Curation Staging"  --organization 'princeton.edu' --contact-email lsupport@princeton.edu --info-link \https://pdc-describe-staging.princeton.edu/about --description "S3 bucket for pre curation data " --keywords princeton.edu,RDOS,research  --allow-guest-collections --user-message "Staging data!  Please do not store production data here" --enable-https
         ```
         **Note** the id returned by this command, you will need it in the next step

   1. Assign the collection id to a variable
          ```
          export collection_id=<output from above command>
          ```
   1. Add administrators via the command line
            ```
            sudo globus-connect-server collection role create $collection_id administrator rdssglobus@princeton.edu
            sudo globus-connect-server collection role create $collection_id administrator cac9@princeton.edu
            sudo globus-connect-server collection role create $collection_id administrator fkayiwa@princeton.edu
            sudo globus-connect-server collection role create $collection_id administrator bs3097@princeton.edu
            sudo globus-connect-server collection role create $collection_id administrator hc8719@princeton.edu
            sudo globus-connect-server collection role create $collection_id administrator jrg5@princeton.edu
            sudo globus-connect-server collection role create $collection_id administrator kl37@princeton.edu
            ```
         

   1. visit the collection on https://app.globus.org/collections?scope=administered-by-me
      1. setup the credentials for accessing s3 (utilize the IAM key from ` ansible-vault edit group_vars/globus/vault.yml`)


### Create a guest Collection for public access to the mapped collection
  ** this is a manual step **

   1. visit https://app.globus.org/collections?scope=administered-by-me
   1. click on the collection you just created
   1. click on the collections tab
   1. click on "Add a guest Collection"
   1. click bowse and select the s3 bucket top path
   1. Fill in the name and description **TBD**
   1. Click create collection
   1. Click "Add Permissions - Share With"
   1. Choose "Public"
   1. Click write if this is an upload collection
   1. Click Add Permissions