# Monitoring in RDSS
## Goals of monitoring:
1. We should know before our users do when there is a problem with systems we manage.
2. During emergency production outages, we should have information to help us resolve the issue quickly.
3. During development, we should have performance telemetry telling us whether the systems we are building will scale and perform as needed.

## The Monitoring Systems
1. [Honeybadger](https://app.honeybadger.io) - for capturing exceptions in a running application. This makes it easier for us to fix bugs, because it gives us a stack trace and lots of context about how the exception occurred. We sometimes use honeybadger uptime monitoring too, but it is very simple (just a binary Up or Down) and only works for systems that are available on the open Internet. New staff need to be added to Honeybadger manually. It is also advisable that each team member subscribe to uptime notifications via email or SMS.
2. [DataDog](https://app.datadoghq.com) - for Application Performance Monitoring (APM). This service can be expensive, so we only turn it on as needed, and [we follow practices to keep costs down](https://github.com/pulibrary/pul-it-handbook/blob/main/services/datadog.md#tips-for-controlling-costs). However, it can be invaluable for diagnosing performance issues.
3. [Sensu](https://lib-monitor.princeton.edu/) - We want to use Sensu for most system monitoring, e.g., disk space, application responsiveness, TLS cert expiration, generally whether the application is running as expected. We are in the process of migrating some monitoring tasks from Honeybadger and DataDog to Sensu.

**Note**: To log into Sensu, use your Princeton SSO credentials, and then check your 2-factor device. It requires 2-factor auth but the login process doesn't indicate this well.

## Monitoring by Application Group
### Princeton Data Commons (PDC*)
The suite of applications that make up the Princeton Data Commons include (so far):
* PDC Discovery
  * Our current setup is to check the application once a minute and report after two failures (i.e. we get notified after two minutes), see [PDC Discovery Monitoring](https://github.com/pulibrary/pdc_discovery#monitoring).
* PDC Describe
  * [PDC Describe DataDog Dashboard](https://app.datadoghq.com/dashboard/ys9-2u3-i84/rdss-monitoring?from_ts=1684345124388&to_ts=1684348724388&live=true)
  * [PDC Describe Hosts on DataDog](https://app.datadoghq.com/infrastructure?tags=application%3Apdc-describe)
