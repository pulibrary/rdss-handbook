# Globus Command Line Interface

Globus provides a command line interface (CLI) to perform operations via the terminal.

## Pre-requisites
The Globus CLI is a Python program and you need to install it first as indicated on the [Globus CLI](https://docs.globus.org/cli/) documentation.

Once installed, make sure to follow the steps indicated on the [Quick Start Guide](https://docs.globus.org/cli/quickstart/) to make sure you can authenticate to Globus with the CLI tool.


## Get a list of files from a Globus endpoint

To get a list of files from an endpoint we can run the `globus ls` command (see [guide](https://docs.globus.org/cli/reference/ls/))
```
globus ls ENDPOINT-ID
```

for example:
```
globus ls 4cea621e-c588-41f4-888e-0f79d229ff84
```

The first time we run it you might get an error message that ask you to run the `session consent` command, for example:

```
globus session consent 'urn:globus:auth:scope:transfer.api.globus.org:all[*https://auth.globus.org/scopes/4cea621e-c588-41f4-888e-0f79d229ff84/data_access]'
```

This will launch your browser and ask you to confirm that you want to allow this kind of access.

After that you can list files from the endpoint:

```
globus ls 4cea621e-c588-41f4-888e-0f79d229ff84:/pdc-describe-staging-precuration/10.34770/r75s-9j74/390
```

and you can do it recursively via the `-r` and  `--recursive-depth-limit` parameters:

```
globus ls -r --recursive-depth-limit=100 4cea621e-c588-41f4-888e-0f79d229ff84:/pdc-describe-staging-precuration/10.34770/r75s-9j74/390
```

**NOTE:** Be aware that, by default, the `-r` parameter will only go three levels down, you must use the `--recursive-depth-limit` if you want to go deeper.


## Get a count of files from a Globus endpoint
There is no built-in command to get a count of files but you can get to this by piping the output to `wc -l` as shown below:

```
globus ls -r --recursive-depth-limit=100 4cea621e-c588-41f4-888e-0f79d229ff84:/pdc-describe-staging-precuration/10.34770/r75s-9j74/390 | wc -l
```


## A complete example
Below is a sample script to get the counts for files for a given DOI in the Princeton Research Data Repository endpoint in Globus. Files for each DOI is stored on a separate folder.

Notice that Globus list folders by themselves and then the files for the folders so the counts with `globus ls -r` have more files than expected. The script gets a separate count for `files` vs `files and folders`.

```
DOI="60j3-yp02"

# Princeton Research Data Repository
GLOBUS_ENDPOINT="dc43f461-0ca7-4203-848c-33a9fc00a464"

echo $DOI
globus ls -r --recursive-depth-limit=100 $GLOBUS_ENDPOINT:/$DOI > $DOI.txt

FILES=`cat $DOI.txt | grep -v '/$' | wc -l`
FILES_FOLDERS=`cat $DOI.txt | wc -l`

echo $FILES
echo $FILES_FOLDERS
```
