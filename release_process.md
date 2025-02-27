## Release and deployment process

- PRs may be deployed to `staging` before merge to confirm they work in that environment.
- Most PRs (beyond documentation changes) should be deployed to `production` after merge to get features out to users.
- Most redeployments will also be new versioned releases, but a release is not strictly necessary for every redeployment.

### Release schedule

- Software releases are made in advance of Feature Refinement meetings with Product Owners.  This is managed through an automated reminder on the RDSS team Slack channel the morning prior.  Whoever acknowledges the reminder first is taking point on putting out the release by doing so.  Any additional features/bug fixes/code work that happens after the release is not guaranteed as a subject of review during the next day's meeting. 
- As much as possible, software releases of completed features and bug fixes are completed the day before expected demos, such as during the RDOS Repository Roundup meeting or larger public demos.  The team self manages in terms of reminding each other and taking point on performing these releases/being aware of the state of the software in the leadup to the demo.

### Release

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

After you have successfully deployed to both `staging` and `production`, and have reviewed the application in the browser to check for any bugs present, send deployment notes generated from the `Releases` page of the latest version in Github and paste them to the `#digital_open_data_and_research` [Slack channel](https://pulibrary.slack.com/archives/C01555TP6HE). 
