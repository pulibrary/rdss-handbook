## Thesis DB Server

We have an implementation of PostgreSQL version 9.2. This is needed because our Vireo will not run with newer versions of PostgreSQL. We need to install PostgreSQL on an EC2 instance that we will manage

## Install PostgreSQL

Install PostgreSQL 9 with the following.

```zsh
yum list available | grep postgresql
```

Ensure you install the resulting version on PostgreSQL 9 from your results.

## Configure PostgreSQL

Find the `postgresql.conf` file and make sure the installation is listening on all interfaces. You will need to uncomment

```conf
#listen_address = 'localhost'
```

to say

```conf
listen_address = '*'
```

Restart the PostgreSQL server when you make these changes. Add the corresponding application server IP address on the `pg_hba.conf` file.

## Setup pg_back

Install by downloading the most current release of [pg_back](https://github.com/orgrim/pg_back/releases) on your EC2 instance. 

Edit and/or create the [configuration file](https://github.com/orgrim/pg_back/blob/master/pg_back.conf)

You will need to add the following changes to the file above

```conf
exclude_dbs = postgres, template0
format = plain
checksum_algorithm = sha512
```

Create the backup directory

```zsh
sudo mkdir -p /var/backups/postgresql
sudo chown -R postgres:postgres /var/backups
```

## Setup gsutil

Run the following command to set up a new repo

```zsh
sudo tee -a /etc/yum.repos.d/google-cloud-sdk.repo << EOM
[google-cloud-cli]
name=Google Cloud CLI
baseurl=https://packages.cloud.google.com/yum/repos/cloud-sdk-el8-x86_64
enabled=1
gpgcheck=1
repo_gpgcheck=0
gpgkey=https://packages.cloud.google.com/yum/doc/rpm-package-key.gpg
EOM
```

Install google-cloud-cli

```zsh
sudo yum -y install google-cloud-cli
```

Create a [service account](https://console.cloud.google.com/projectselector/iam-admin/serviceaccounts/create?walkthrough_id=iam--create-service-account#step_index=1) and a generate a key for your service account. You will need this key to complete setup of your service account. 

With the key above, activate your account (as the postgres user)

The `--key-file` in the example below will be named `postgres_user.json` run the following commands:

```zsh
sudo su - postgres
mkdir {logs,.config}
vi ~/.config/postgres_user.json # enter file content
gcloud auth activate-service-account --key-file .config/postgres_user.json --project=pul-gcdc
```

Create a [Google Cloud Bucket](https://console.cloud.google.com/storage/browser)



## Set Up Backup

Run the pg_back program to do an initial backup

```zsh
pg_back
```

when it completes, ensure that you can sync the content to google cloud with 

```zsh
/usr/bin/gsutil rsync -ru /var/backups/postgresql gs://google-bucket-name
```

create a cron job to run daily with the following

```zsh
# backup
25 4 * * * /usr/bin/pg_back
#
# m h  dom mon dow   command
25 5 * * * /usr/bin/gsutil rsync -ru /var/backups/postgresql gs://google-bucket-name > ~/logs/gsutil.log 2>&1
```