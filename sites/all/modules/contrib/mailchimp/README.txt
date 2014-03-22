----
WARNING:
This is an ALPHA release of MailChimp 7.x-3.0. If you want a stable Mailchimp
integration, start with 7.x-2.14. If you need MailChimp integration with
non-user entities and want to help test the 3.x branch, this is a good starting
point. This is not intended as a stable release, though, so proceed with
caution!
----

This module provides integration with the MailChimp email delivery service.
While tools for sending email from your own server, like SimpleNews, are great,
they lack the sophistication and ease of use of dedicated email providers like
MailChimp. Other players in the field are Constant Contact and Campaign Monitor.

mailchimp.module provides provides basic configuration and API integration.
Specific functionality is provided by a set of submodules that depend upon
mailchimp.module. See their respective README's for more details.

## Features
  * API integration
  * Support for an unlimited number of mailing lists
  * Have anonymous sign up forms to subscribe site visitors to any combination
    of Mailchimp lists
  * Mailchimp list subscription via entity fields, allowing subscription rules
    to be governed by entity controls, permissions, and UI
  * Compatibility with Views Bulk Operations
  * Special VBO function for creating & updating static list segments
  * Allow users to subscribe during registration by adding a field to Users
  * Map Entity field values to your MailChimp merge fields
  * Standalone subscribe and unsubscribe forms
  * Subscriptions can be maintained via cron or in real time
  * Subscription forms can be created as pages or as blocks, with one or more
    list subscriptions on a single form
  * Include merge fields & interest groups on anonymous subscription forms

## Installation Notes
  * You need to have a MailChimp API Key.
  * You need to have at least one list created in MailChimp to use the
    mailchimp_lists module.
  * The MCAPI library must be downloaded into your libraries folder. 7.x-3.x
    uses the 2.0.x version of the Mailchimp API, where 7.x-2.x used the 1.3
    version. Make sure you have the new version. It's available at:
    https://bitbucket.org/mailchimp/mailchimp-api-php/downloads or by using the
    included example drush make file. Proper libraries structure:
    - libraries/
      - README.md
      - composer.js
      - mailchimp/
        - src/
          - Mailchimp.php
          - Mailchimp/
  * At the time of writing, version 2.0.4 of the Mailchimp API library was the
    latest. If you are using a later version and have issues, consider switching
    to version 2.0.4.

## Configuration
  1. Direct your browser to http://example.com/admin/config/services/mailchimp
  to configure the module.

  2. You will need to put in your Mailchimp API key for your Mailchimp account.
  If you do not have a Mailchimp account, go to
  [http://www.mailchimp.com]([http://www.mailchimp.com) and sign up for a new
  account. Once you have set up your account and are logged in, visit:
  Account Settings -> Extras -> API Keys to generate a key.

  3. Copy your newly create API key and go to the
  [Mailchimp config](http://example.com/admin/config/services/mailchimp) page in
  your Drupal site and paste it into the Mailchimp API Key field.
  Batch limit - Maximum number of changes to process in a single cron run.
  Mailchimp suggest keeping this below 5000-10000.

## Submodules
  * mailchimp_signup: Create anonymous signup forms for your Mailchimp Lists,
    and display them as blocks or as standalone pages. Provide multiple-list
    subscription from a single form, include merge variables as desired, and
    optionally include Interest Group selection.
  * mailchimp_lists: Subscribe any entity with an email address to MailChimp
    lists by creating a mailchimp_list field, and allow anyone who can edit such
    an entity to subscribe, unsubscribe, and update member information. Also
    allows other entity fields to be synced to Mailchimp list Merge Fields.

## Testing
(todo)

## Related Modules
### Mandrill
  * Mandrill is MailChimp's transactional email service. The module provides the
    ability to send all site emails through Mandrill with reporting available
    from within Drupal. Please refer to the project page for more details.
  * http://drupal.org/project/mandrill
### MCC, an alternative campaign creation tool.
  * http://drupal.org/project/mcc
