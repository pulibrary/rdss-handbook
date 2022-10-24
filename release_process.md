## Release and deployment process

- PRs may be deployed to `staging` before merge to confirm they work in that environment.
- Most PRs (beyond documentation changes) should be deployed to `production` after merge to get features out to users.
- Most redeployments will also be new versioned releases, but a release is not strictly necessary for every redeployment.

### Release

#### Release pre-requisites

We use [Intuit Auto](https://intuit.github.io/auto/) to automate the deployment. To install 'auto' [via brew](https://intuit.github.io/auto/docs/configuration/non-npm):

1. `brew tap intuit/auto https://github.com/intuit/auto`
1. `brew install auto`
1. [Create a new Github Token](https://github.com/settings/tokens) with `write:packages` privs.
1. Add the token to the approapriate startup file for your shell. Something like: `echo 'export GH_TOKEN="YourTokenHere"' >> ~/.bash_profile`

#### Release process

* `git checkout main`
* `git tag -l` will show what tags exist
* `git tag <versionOfTheTag>` create the tag
* `git push --tags` push the new tag on Github
* `auto release` will create a new release on Github
* Review the generated release notes and edit as needed

### Deployment

#### Deployment pre-requiusites

Deployments are done with `pulbot`: You'll need to be added to the `#robots` channel in PULibrary slack.
Once you're added, try `pulbot deploy pdc_describe to staging`: You'll get an error message like:
> I'm sorry, @UserName (U0123456789), but you don't have access to do that.

Copy the ID that looks like `U0123456789`, and make a PR to update the [list of allowed users](https://github.com/pulibrary/pulbot/blob/main/scripts/listener_middleware.coffee).
A peer who already has privs should merge your PR, and redeploy pulbot itself with `pulbot deploy pulbot`.
When the pulbot redeploy is complete you'll be able to complete your deploy to staging.

### Deployment process

Deployments are done using pulbot on Slack.

Staging can be used to demo the work on a feature branch:
```
pulbot deploy repo-name/branch-name to staging
```

Or staging can be used after the branch is merged to main:
```
pulbot deploy repo-name to staging
```

After confirming that it looks good on staging, deploy to production:
```
pulbot deploy repo-name/v1.2.3 to production
```
