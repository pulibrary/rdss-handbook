# Plausible

[Plausible.io](https://plausible.io/) is an Open Source web analytics service that is considered a privacy-friendly alternative to Google Analytics. It is currently in use in the following application(s) at PUL:

- [PDC_Discovery](https://github.com/pulibrary/pdc_discovery)

## Managing users and accessing the dashboard

Users can sign up for a free Plausible account at [Plausible.io](https://plausible.io/). To access sites, users must be invited as either an admin or a viewer. Admins can view the data dashboard, add more users, and adjust site settings. Viewer have read-only access to the data dashboard.

_NOTE: Plausible site invitations may go to the user's Junk/Spam folder._

## Managing API keys

To create API keys, go to your [Plausible user account settings](https://plausible.io/settings) (_not_ an individual site's settings) and scroll down to the "API keys" section. Click the "+ New API Key" button to name and create a new API key.

**_WARNING_**: You must copy the API key from this screen at this step. This is the only time that the API key will be visible in Plausible!

Once you have created and copied the API key, store it in LastPass immediately.

You can also delete API keys by selecting the "Revoke" option in the "API keys" section of the Plausible user account settings page. Users can create as many API keys as desired, and the keys can be used for any site for which the user is an admin in Plausible.

## Managing sites

To add a new site, log into Plausible and navigate to the [homepage](https://plausible.io/), then click the "Add a new website+" button. You will be asked to supply the site domain and timezone. Once you have input these, you will receive the Javascript snippet to embed in your site to begin tracking.

### Managing the Plausible subscription

PUL has a premium subscription to Plausible through our Library IT Operations team. In order for new sites to be included in this subscription, the organization cardholder must be the site "owner" in Plausible. After creating a new site, complete the following steps to add it to the premium subscription:

- Invite the cardholder to the new site as an Admin, through the that site's "Settings / Users" section. This will send them an email.

  _NOTE: Plausible emails tend to go to Junk/Spam folders. If they do not receive the email within a couple of minutes of the invitation being issued, check there._

- Once the cardholder accepts this invitation, send them a site ownership transfer from the same "Settings / Users" section of the new site in Plausible.

  _NOTE: That, too, may go to Junk._

- Once the cardholder accepts the ownership transfer, admins and viewers on that site should be able to go to the site in Plausible and see the dashboard, example below:

![](images/plausible_dashboard.png)

## Custom properties
We use custom properties to track download events in [PDC_Discovery](https://github.com/pulibrary/pdc_discovery).

To *define* custom properties you need to go to the Settings page for the site:

![](images/plausible_custom_properties_define.png)

To *view the values* collected for the custom property you go to the Custom Properties in the home page and select the "Properties" option

![](images/plausible_custom_properties_view.png)
