# Runner Role

RDSS employs the time of a Runner in each sprint, to ensure that errors encountered in any of our applications are ticketed and appropriately prioritized, so that bugs and other issues are routinely addressed.

## Norms and Duties

There is one runner per sprint.  The new runner is selected during the [Sprint Planning meeting](meetings.md), which occurs once every two weeks at the beginning of a new sprint.

The runner's duties are as follows:

Each workday check:

* [Honeybadger](https://app.honeybadger.io/projects) for *errors* in the following RDSS applications:
   * [globus uptime](https://app.honeybadger.io/projects/103564/sites)
   * [orcid errors](https://app.honeybadger.io/projects/114910/faults?q=-is%3Aresolved+-is%3Aignored) and [orcid uptime](https://app.honeybadger.io/projects/114910/faults?q=-is%3Aresolved+-is%3Aignored)
   * [openpublishing uptime](https://app.honeybadger.io/projects/93417/sites/0f636d4c-7961-4c35-aece-0e58925491bd)
   * [pdc_describe errors](https://app.honeybadger.io/projects/99214/faults?q=-is%3Aresolved+-is%3Aignored&sort=last_seen_asc) and [pdc_describe uptime](https://app.honeybadger.io/projects/99214/sites)
   * [pdc_discovery errors](https://app.honeybadger.io/projects/95072/faults?q=-is%3Aresolved+-is%3Aignored) and [pdc_discovery uptime](https://app.honeybadger.io/projects/95072/sites)
   * [tigerdata errors](https://app.honeybadger.io/projects/113559/faults?q=-is%3Aresolved+-is%3Aignored) and [tigerdata uptime](https://app.honeybadger.io/projects/113559/sites)
* [Honeybadger](https://app.honeybadger.io/projects) for *uptime errors* in PDC Globus. We should be getting emails when an application goes down, but it does not hurt to check as part of the runner dutties.
* Check [DataDog](https://app.datadoghq.com/logs?saved-view-id=2137895) for errors in RDSS applications.
* Create a ticket for each error encountered, if one does not already exist.
* Bring error tickets to the RDSS team's attention at check-in for prioritization.
* If a ticket is a work-stopping issue/considered high priority and is therefore assigned to the current sprint, it receives the "unplanned work" [label](sprints.md) in GitHub.
* In the ticket, include a checkbox to mark the issue resolved in Honeybadger as part of the acceptance criteria if appropriate ([example here](https://github.com/pulibrary/pdc_describe/issues/1513)).

* Check the failed jobs queue for PDC Describe in production. See [details](https://github.com/pulibrary/pdc_describe/blob/main/docs/sidekiq_jobs.md)

* Review and merge [dependabot PRs in our repositories](https://github.com/pulls?q=is%3Aopen+is%3Apr+draft%3Afalse+repo%3Apulibrary%2Fpdc_describe+repo%3Apulibrary%2Fpdc_discovery+repo%3Apulibrary%2Fannotations_app+repo%3Apulibrary%2Fdataspace_embargo_lifter+repo%3Apulibrary%2Fdspace-cli+repo%3Apulibrary%2Fdspace-development+repo%3Apulibrary%2Fdspace-java+repo%3Apulibrary%2Fdspace-jruby+repo%3Apulibrary%2Fetd_transformer+repo%3Apulibrary%2Foawaiver+repo%3Apulibrary%2Fopenbooks+repo%3Apulibrary%2Fopenpublishing+repo%3Apulibrary%2Fouranos+repo%3Apulibrary%2Frdss-handbook+repo%3Apulibrary%2FSimpleAnnotationServer+repo%3Apulibrary%2Ftiger-data-app+repo%3Apulibrary%2Ftiger-data-experiments+sort%3Acreated-asc+). Make sure they pass CI and deploy them to staging before merging them.
