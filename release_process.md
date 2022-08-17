## Create a new tag and a new release
  We create a new release before deploying software to our production servers.  In general we should release and deploy for each bug fix, or feature that is completed.

### Pre-requisites
We use [Intuit Auto](https://intuit.github.io/auto/) to automate the deployment. To install 'auto' [via brew](https://intuit.github.io/auto/docs/configuration/non-npm):

1. `brew tap intuit/auto https://github.com/intuit/auto`
1. `brew install auto`
1. You will also need to create a GitHub token as indicated [here](https://intuit.github.io/auto/docs/configuration/non-npm#configuration).

### To create and publish the tagged release
* `git checkout main`
* `git tag -l` will show what tags exist
* `git tag <versionOfTheTag>` create the tag
* `git push --tags` push the new tag on Github
* `auto release` will create a new release on Github

### Process
1. Tag the release.
1. Review the release notes on GitHub, update wording as needed.
1. Deploy the tagged release on staging and check that everything looks good once it's done.
1. If everything looks good on staging, deploy the tagged release to production.
1. Post a notice to the appropriate PUL Slack channel that the release has been deployed to staging and production.  Make sure it contains the following information:
  - The release number
  - Where it has been deployed (staging, production, or both)
  - Whether this is a "bugfix," "feature," or "major" release
  - List of items included in the release notes
