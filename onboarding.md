# RDSS Onboarding

When a new staff member joins RDSS here are some tasks that need to happen for them to have the right access:

1. On their development machine, confirm that the user account has admin access, and that [homebrew](https://brew.sh/) can be installed. (Laptops configured by PUL will typically give the user admin access, but this is not the default for OIT laptops.)
1. Add github account to `pulibrary` organization.
1. Add their account to [the shared `.gitmessage`](https://github.com/pulibrary/pul-the-hard-way/blob/main/gitmessage.md)
1. Set up AWS permissions for RDSS S3 access (see instructions below)

## AWS Setup for S3 access

RDSS maintains S3 buckets on AWS for storing research data. Here are the necessary steps to set up a new user with the correct permissions to help maintain these.

### 1. Set up AWS account

1. Go to [https://princeton.edu/aws](https://princeton.edu/aws) and log in with Princeton credentials.
2. From the "Services" menu, select "IAM". (You might need to search for IAM in the search bar.) Under the "User" menu, create a new user. Use any user name you prefer, as long as it would be clear to your team mates that this name is associated with you. Choose AWS credential type "Access Key". Add the new account to the group `rdss`.
3. Record the Access Key ID and the Secret access key you'll get on the `Success` screen. You will need to add these to your local user profile when you set up AWS command line access.

### 2. Install and configure aws cli

1. Install the aws cli: https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
2. Configure it using the Access key ID and Secret Access key attached to your account. Do this by running `aws configure` or following instructions [here](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-quickstart.html).

- Use default region `us-east-1`
- Use default format `json`

3. You will also need to install jq: `brew install jq` (assuming you use homebrew)

### 3. Test whether it worked

You should be able to issue this command:

```
aws ec2 describe-instances --query 'Reservations[*].Instances[?not_null(PublicIpAddress)]' | jq -r '.[][]|.PublicIpAddress+" "+(.Tags[]|select(.Key=="Name").Value)'
```

And see something like this:

```
54.226.248.201 prds-dataspace-endpoint1
52.91.144.13 prds-dataspace-dtn1
107.22.149.128 prds-dataspace-staging-endpoint1
52.87.245.81 pdc-globus-staging
```
