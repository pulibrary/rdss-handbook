## Create a new tag and a new release

### Pre-requisites
We use [Intuit Auto](https://intuit.github.io/auto/) to automate the deployment. To install 'auto' [via brew](https://intuit.github.io/auto/docs/configuration/non-npm):

* `brew tap intuit/auto https://github.com/intuit/auto`
* `brew install auto`

### To create and publish the tagged release
* `git checkout main`
* `git tag -l` will show what tags exist
* `git tag <versionOfTheTag>` create the tag
* `git push --tags` push the new tag on Github
* `auto release` will create a new release on Github
