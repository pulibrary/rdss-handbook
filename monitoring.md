# Monitoring in RDSS

## Where to start
Look here first: [RDSS Portfolio in Checkmk staging](https://pulmonitor.princeton.edu/staging/check_mk/index.py?start_url=%2Fstaging%2Fcheck_mk%2Fview.py%3Ffilled_in%3Dfilter%26_active%3Dwato_folder%253Bhostregex%253Bsiteopt%26wato_folder%3Dlinux%252Frdss%26selection%3De08a41a0-c1aa-45eb-9f73-477304274492%26view_name%3Dallhosts%26_show_filter_form%3D1)
| [RDSS Portfolio in Checkmk Production](https://pulmonitor.princeton.edu/production/check_mk/index.py?start_url=%2Fproduction%2Fcheck_mk%2Fview.py%3Ffilled_in%3Dfilter%26_active%3Dwato_folder%253Bhostregex%253Bsiteopt%26wato_folder%3Dlinux%252Frdss%26selection%3Ddf1b3c63-821f-4ace-a209-b25a36bf138e%26view_name%3Dallhosts%26_show_filter_form%3D1)

## Goals of monitoring:
1. We should know before our users do when there is a problem with systems we manage.
2. During emergency production outages, we should have information to help us resolve the issue quickly.
3. During development, we should have performance telemetry telling us whether the systems we are building will scale and perform as needed.

## Where the Alerts Go
All alerts should go to the #rdss-alerts channel in slack

## The Monitoring Systems
1. [Checkmk](https://pulcheck-staging.princeton.edu/pulmonitor/) - Our primary monitoring system. This is for capturing uptime of our application hosts, service health for our applications. We will also be able to use Checkmk for Application Performance Monitoring as we integrate more of our portfolio onto the platform. Notifications from Checkmk are sent to the `rdss-alerts` channel for our staging hosts, and `rdss-incidents` for our production hosts. To adjust the frequency of these notifications, we can edit the notification rules for the host located in the events submenu of the setup panel. [Notifications](https://pulmonitor.princeton.edu/production/check_mk/index.py?start_url=%2Fproduction%2Fcheck_mk%2Fwato.py%3Fmode%3Dnotifications) Honeybadger and DataDog uptime alerts should move here.
2. [Honeybadger](https://app.honeybadger.io) - for capturing exceptions in a running application. This makes it easier for us to fix bugs, because it gives us a stack trace and lots of context about how the exception occurred. We sometimes use honeybadger uptime monitoring too, but it is very simple (just a binary Up or Down) and only works for systems that are available on the open Internet. New staff need to be added to Honeybadger manually. It is also advisable that each team member subscribe to uptime notifications via email or SMS.
3. [DataDog](https://app.datadoghq.com) - for Application Performance Monitoring (APM). This service can be expensive, so we only turn it on as needed, and [we follow practices to keep costs down](https://github.com/pulibrary/pul-it-handbook/blob/main/services/datadog.md#tips-for-controlling-costs). However, it can be invaluable for diagnosing performance issues.

## Monitoring by Application Group
### Princeton Data Commons (PDC*)
The suite of applications that make up the Princeton Data Commons include (so far):
* PDC Discovery
  * Our current setup is to check the application once a minute and report after two failures (i.e. we get notified after two minutes), see [PDC Discovery Monitoring](https://github.com/pulibrary/pdc_discovery#monitoring).
* PDC Describe
  * [PDC Describe DataDog Dashboard](https://app.datadoghq.com/dashboard/ys9-2u3-i84/rdss-monitoring?from_ts=1684345124388&to_ts=1684348724388&live=true)
  * [PDC Describe Hosts on DataDog](https://app.datadoghq.com/infrastructure?tags=application%3Apdc-describe)
### ORCID
The suite of applications that make up ORCID include (so far):
* ORCID
  * [ORCID Checkmk Dashboard](https://pulmonitor.princeton.edu/production/check_mk/index.py?start_url=%2Fproduction%2Fcheck_mk%2Fview.py%3Fhost%3Dorcid.princeton.edu%26site%3Dproduction%26view_name%3Dhoststatus)
  * [ORCID Honeybadger Dashboard](https://app.honeybadger.io/projects/114910/insights/dashboards)