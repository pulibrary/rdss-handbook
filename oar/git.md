# Open Access Repository (OAR)

## Code Base

As originally OAR was a project maintained by the Princeton University Office of Information Technology, the code base for this project was maintained within a private institutional BitBucket account (this has since been removed entirely). From August 2019 onwards, Princeton University Library decided to commit to collaborating with an external contracting firm, with the aim of maintaining the code base, and, ultimately, migrating to upgraded releases of DSpace. As such, this form migrated the code base to a `git` repository which was hosted using a deployment of [GitLab hosted and maintained by this enterprise](https://git.atmire.com/clients/princeton-5). From October 2021 onwards, there was a need to shift exclusively towards maintaining the code base locally, and the git repository was mirrored to the [GitHub Organization reserved for privately-accessible projects](https://github.com/PrincetonUniversityLibrary/princeton-5).

In order to facilitate with this migration, the `git remote` URIs needed to be updated for the current server environments. The remote `origin` was renamed to `atmire`, with the `PrincetonUniversityLibrary` mirror added as the new `origin` remote.

### oar-dev.princeton.edu

```bash
dspace@gcp-oar-dev1:~/src$ git remote -v
atmire  https://princeton:$SECRET@git.atmire.com/clients/princeton-5.git (fetch)
atmire  https://princeton:$SECRET@git.atmire.com/clients/princeton-5.git (push)
origin  https://jrgriffiniii:$SECRET@github.com/PrincetonUniversityLibrary/princeton-5.git (fetch)
origin  https://jrgriffiniii:$SECRET@github.com/PrincetonUniversityLibrary/princeton-5.git (push)
```

### oar-staging.princeton.edu

```bash
dspace@gcp-oar-staging1:~/src$ git remote -v
atmire  https://princeton:$SECRET@git.atmire.com/clients/princeton-5.git (fetch)
atmire  https://princeton:$SECRET@git.atmire.com/clients/princeton-5.git (push)
origin  https://jrgriffiniii:$SECRET@github.com/PrincetonUniversityLibrary/princeton-5.git (fetch)
origin  https://jrgriffiniii:$SECRET@github.com/PrincetonUniversityLibrary/princeton-5.git (push)
```

### oar.princeton.edu

```bash
dspace@gcp-oar-prod1:~/src$ git remote -v
atmire  https://princeton:$SECRET@git.atmire.com/clients/princeton-5.git (fetch)
atmire  https://princeton:$SECRET@git.atmire.com/clients/princeton-5.git (push)
origin  https://jrgriffiniii:$SECRET@github.com/PrincetonUniversityLibrary/princeton-5.git (fetch)
origin  https://jrgriffiniii:$SECRET@github.com/PrincetonUniversityLibrary/princeton-5.git (push)
```
