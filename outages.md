# Dealing with outages

We are still tuning our process to deal with application outages, some applications (like PDC Discovery) are monitored with Honeybadger.


## Using Honeybadger Uptime
[Honeybadger](https://app.honeybadger.io/) has a feature to monitor that applications are up and running and it can send notifications when the application does not respond.

Our current setup is to check the application once a minute and report after two failures (i.e. we get notified after two minutes), see [PDC Discovery Monitoring](https://github.com/pulibrary/pdc_discovery#monitoring).

We configure applications to send a message to the Slack `#rdss-team` channel.

It is also advisable that each team member subscribe to uptime notifications via email.
