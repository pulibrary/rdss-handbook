# Runner Role

RDSS employs the time of a Runner in each sprint, to ensure that errors encountered in any of our applications are ticketed and appropriately prioritized, so that bugs and other issues are routinely addressed.

## Norms and Duties

There is one runner per sprint.  The new runner is selected during the [Sprint Planning meeting](meetings.md), which occurs once every two weeks at the beginning of a new sprint.

The runner's duties are as follows:
* Each workday, check Honeybadger and [DataDog](https://app.datadoghq.com/logs?saved-view-id=2137895) for errors in RDSS applications.
* Create a ticket for each error encountered, if one does not already exist.
* Bring error tickets to the RDSS team's attention at check-in for prioritization.
* If a ticket is a work-stopping issue/considered high priority and is therefore assigned to the current sprint, it receives the "unplanned work" [label](work_cycles.md) in GitHub.
* In the ticket, include a checkbox to mark the issue resolved in Honeybadger as part of the acceptance criteria if appropriate ([example here](https://github.com/pulibrary/pdc_describe/issues/1513)).

* Check the failed jobs queue for PDC Describe in production. See [details](https://github.com/pulibrary/pdc_describe/issues/1574#issuecomment-1773374397)
