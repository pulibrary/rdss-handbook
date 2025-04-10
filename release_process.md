## Release and deployment process

- PRs may be deployed to `staging` before merge to confirm they work in that environment.
- Most PRs (beyond documentation changes) should be deployed to `production` after merge to get features out to users.
- Most redeployments will also be new versioned releases, but a release is not strictly necessary for every redeployment.

### Release Process

#### Release pre-requisites

We use [Intuit Auto](https://intuit.github.io/auto/) to automate the deployment. To install 'auto' [via brew](https://intuit.github.io/auto/docs/configuration/non-npm):

1. `brew tap intuit/auto https://github.com/intuit/auto`
1. `brew install auto`
1. [Create a new Github Token](https://github.com/settings/tokens) with `write:packages` privs.
- When creating a new token, select `Generate new token (classic)`
- For the note section of the new token, add something like `RDSS Release Process` to help identify what this token is used for. 
- For the privs section, select the following: Under "repo" `repo:status`, `repo_deployment`, `public_repo`. Selecting these will ensure that you will have the appropriate access to deploying RDSS applications.
1. Add the token to the approapriate startup file (e.g. .bash_profile, .zshrc) for your shell. Something like: `echo 'export GH_TOKEN="YourTokenHere"' >> ~/.bash_profile`

#### Release process

- `git checkout main`
- `git pull` for latest changes to `MAIN` branch
- `git tag -l` will show what tags exist
    - For information on the latest release to know what the new version of the tag should be, you may navigate to the Releases section in the repository of the application you want to deploy. The version will be displayed on the right side of the repository in Github. 
- `git tag <versionOfTheTag>` create the tag
- `git push --tags` push the new tag on Github
- `auto release` will create a new release on Github
- Review the generated release notes and edit them as needed

### Deployment

#### Deployment pre-requiusites

#### Deployment process

For the deployment process to be completed, once you have generated the release notes on Github, you are then able to deploy. 

From the `MAIN` branch, execute the following: `BRANCH=<versionOfTheTag> bundle exec cap staging deploy`

Review these changes on the appropriate staging environment, and if you run into any bugs or unexpected results, please let someone on the RDSS team know as soon as possible. There may need to be a ticket created to address this bug. 

If there are no issues with your latest deployment after reviewing `staging`, you may deploy those changes to `production`

`BRANCH=<versionOfTheTag> bundle exec cap production deploy`

##### Deploy production a single machine at a time
We would reccomend deploying to each production server separately if this change is also accompanied by a server upgrade.

1. On your local machine in the application directory run capistrano to remove one server from the loadbalancer.  **Note the limit must macth the name of the machine in the 
   config/deploy/production.rb file for the system you are deploying**
   ```
   cap --hosts=orcid-prod1.princeton.edu production application:remove_from_nginx
   ```

1. Run the upgrades to the server via prancible in the princeton_ansible directory limiting to the same machine **Note: orcid-prod1.princeton.edu should change to match the above command**
   ```
   ansible-playbook --limit orcid-prod1.princeton.edu -e runtime_env=production playbooks/orcid.yml
   ```
1. Deploy the software updates via capistrano in the application directory limiting to the same machine **Note: orcid-prod1.princeton.edu should change to match the first command**
   ```
   BRANCH=<versionOfTheTag> bundle exec cap --hosts=orcid-prod1.princeton.edu production deploy
   ```

1. In the application directory run capistrano to put the machine back on the load balancer **Note: orcid-prod1.princeton.edu should change to match the first command**
   ```
   cap --hosts=orcid-prod1.princeton.edu production application:serve_from_nginx
   ```

After you have successfully deployed to both `staging` and `production`, and have reviewed the application in the browser to check for any bugs present, send deployment notes generated from the `Releases` page of the latest version in Github and paste them to the appropriate Slack channel (see "Production Releases" section below, or our [applications portfolio](applications.md)).

### Production releases

Every Tuesday, the following text block is added to the stand-up agenda:

```
 * Production Release and Deployment Tuesday
    * Add your name next to the application you are volunteering to release & deploy!
    * pdc_describe (#digital_open_data_and_research)
    * pdc_discovery (#digital_open_data_and_research)
    * orcid_princeton (#orcid)
    * tigerdata-app (#tigerdata)
    * tigerdata-config (update on private developers Slack channel)
    * oawaiver (#openresearcher)
```

A developer volunteers to release and deploy an application to production by putting their name next to that application in the list. The list is filled out in its entirety during stand-up.

Once the application is deployed to production, the developer who orchestrated the release/deployment posts the release notes and an announcement of the deployment to the appropriate Slack channel (noted next to the name of the application above).

#### Additional norms: 

* The release and deployment is orchestrated by the volunteer at some point during the workday on that same day (Tuesday) in advance of our Wednesday morning meetings with the Product Owner.
* If the production release/deployment exposes a bug in the deployment workflow, the developer should open a ticket for this and bring it to the team’s attention.
* This schedule is for regular production deployments including features and proactively-addressed security concerns; production deployments required to address emergencies should be done as needed outside of this schedule.