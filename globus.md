# Globus

[Globus](https://www.globus.org/data-transfer) is a fast, reliable file transfer service that makes it easy for users to move data between two GridFTP servers or between a GridFTP server and a user's machine (Windows, Mac or Linux). It is increasingly used by researchers to transfer large data sets because it provides faster and more reliable transfers than previous methods.

For a quick intro to Globus take a look at [Globus for newbies](https://docs.google.com/document/d/1d8u3KhsoX-x3k59GgWfhC7325R6616j8RytccTelPWM/edit#).

## Account setup
In order to help maintain our Globus infrastructure you'll need an AWS account with the right permission. See the [onboarding](onboarding.md) documentation for how to set that up.

## Prequisites
  * To build an ami please install the prequisites from https://github.com/pulibrary/vm-builds#prerequisite-software
    * The following steps require awscli which should be installed as part of vm-builds
  * You will be utilizing [princeton-ansible](https://github.com/pulibrary/princeton_ansible#macos).  Please make sure the environment is set up on your local machine

## Data management
Our Globus instance is for research data that has gone through curation. Because 
it has gone through curation, it will always have a [DOI](https://www.doi.org/), and it is organized under its DOI number. 

Data is stored in S3 buckets. We are in the process of building a new Globus production system. (Project plan [here](https://docs.google.com/document/d/13HkbOoC7OLD70FIEwFlHs8zi2Z8h53Puflm7DCcjnSw/edit).)

Our legacy Globus instance has its data in an S3 bucket called `prds-dataspace`.
Our new PDC branded globus instance will have its data in a bucket called `pdc-globus-prod`.

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

## Creating the service account (Not needed each time)
  1. Fillin the ticket in [service now](https://princeton.service-now.com/service?id=sc_cat_item&sys_id=f44539ab4ff81640f56c0ad14210c77c)
      * Duration: Permanent
      * Type: General
      * Service Account User(s): Team members should be added here
## Creating the ami (Not needed each time)

 1. run `packer build aws-globus.pkr.hcl` from the [vm-buids](https://github.com/pulibrary/vm-builds) directory on your local machine
 1. see your new ami in [AWS](https://us-east-1.console.aws.amazon.com/ec2/v2/home?region=us-east-1#Images:visibility=owned-by-me)

## Creating the AWS EC2 instance from AMI

1. In princeton-ansible check the group_vars/globus/common.yml to make sure the image_id matches the ami you either created or are using
1. Run the playbook with either staging (default) or production (`-e runtime_env=production`).  For example the command below will create a staging EC2 instance named  pdc-globus-staging 
   ```
   ansible-playbook playbooks/aws_ec2.yml -e ec2_name=pdc-globus-staging-precuration
   ```

1. See your new instance in [AWS](https://us-east-1.console.aws.amazon.com/ec2/v2/home?region=us-east-1#Instances:instanceState=running)  Note the IP address you will need it to configure Globus in following steps


## Configure Globus Endpoint
To register a Globus Endpoint do the following:
1. Go to [developers.globus.org](https://developers.globus.org), sign in   
2. Add a new Globus Connect Server and fill 2out the form in the **Princeton Data Commmons Production** or **Princeton Data Commmons Staging** Projects. 
   1. Type in the new name
   1. click Register Globus Connect Server 
3. Generate a client secret.  Be ready to save the value off, you will only see it once.
   1. Click Generate a New Client Secret within the new section on the website created by the step above
   1. Fill in the decsription of the secret (can be anything)
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
globus-connect-server login localhost
```