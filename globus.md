# Globus

[Globus](https://www.globus.org/data-transfer) is a fast, reliable file transfer service that makes it easy for users to move data between two GridFTP servers or between a GridFTP server and a user's machine (Windows, Mac or Linux). It is increasingly used by researchers to transfer large data sets because it provides faster and more reliable transfers than previous methods.

For a quick intro to Globus take a look at [Globus for newbies](https://docs.google.com/document/d/1d8u3KhsoX-x3k59GgWfhC7325R6616j8RytccTelPWM/edit#).

## Account setup
In order to help maintain our Globus infrastructure you'll need an AWS account with the right permission. See the [onboarding](onboarding.md) documentation for how to set that up.

## Data management
Our Globus instance is for research data that has gone through curation. Because 
it has gone through curation, it will always have a [DOI](https://www.doi.org/), and it is organized under its DOI number. 

Data is stored in S3 buckets. We are in the process of building a new Globus production system. (Project plan [here](https://docs.google.com/document/d/13HkbOoC7OLD70FIEwFlHs8zi2Z8h53Puflm7DCcjnSw/edit).)

Our legacy Globus instance has its data in an S3 bucket called `prds-dataspace`.
Our new PDC branded globus instance will have its data in a bucket called `pdc-globus-prod`.

### Making a new S3 bucket
To make a new S3 bucket with a copy of the PDC Globus data:
1. Use the AWS console to make a new bucket in the `us-east-1` region. Copy the permissions from the existing `prds-dataspace` bucket. 
2. Copy the data using the aws cli: `aws s3 sync s3://prds-dataspace s3://pdc-globus-prod`

Note that this will take about five hours. 

## Configure Globus Endpoint
To register a Globus Endpoint do the following:
1. Go to [developers.globus.org](developers.globus.org), sign in   
2. Add a new Globus Connect Server and fill out the form in the **Princeton Data Commmons Production** or **Princeton Data Commmons Staging** Projects. 
3. Click **Generate a New Client Secret** and fill out the form. Save the Client ID and Client Secret values.
4. Log into the virtual machine and create a directory called `app_config` and switch into the directory to run:
```bash
globus-connect-server endpoint setup "Princeton Data Commons Globus Staging" \
    --organization "Princeton University Library" \
    --client-id "31uuiddd2a-6199-4c3e-b08f-a4anamec3" \
    --owner your_name@princeton.edu \
    --contact-email any_ops_person@princeton.edu
```
5. Enter secret from step 3. above and **Accept Let's Encrypt ToS** (This will take a while)
6. You will get a response close to this

```bash
Please authenticate with Globus to set the owner of the endpoint:
----------------------------------------------------------------
https://auth.globus.org/v2/oauth2/authorize?client_id=auuid-&redirect_uri=https%3A%2F%2Fauth.globus.org%2Fv2%2Fweb%2Fauth-code&scope=urn%3Aglobus%3Aauth%3Ascope%3Atransfer.api.globus.org%3Aall&state=_default&response_type=code&access_type=online&session_required_identities=uuid&session_message=Set+the+advertised+owner+of+the+endpoint
----------------------------------------------------------------
```
7. Paste the results from your browser to complete endpoint creation.
8. This will create a `deployment-key.json` file in the `app_config` directory. This is an important file that 

## Configure Globus Node
Still in your VM in the `app_config` directory run the following command to configure your node: (note: use of `sudo`)

```bash
sudo globus-connect-server node setup \
    --client-id "3113dd2a-6199-4c3e-b08f-a4ac4b5ae5c3"
```
Finish the setup by running this on the VM

```bash
globus-connect-server login localhost
```