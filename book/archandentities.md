
# Architecture & Entities

In the [Content Management System Overview](../book/cms.md) it was noted that a CMS has a database component and a display component where "There is also code in between the data and display that applies any logic."  Some of that logic might be things you code in to do stuff unique to your website; either coded directly or grabbed from a [contributed module](chapters.md#drupal-modules) that has underlying code accomplishing what you want.   However, before all that happens it is being applied to Drupal's Core.  Understanding some of the logic in what Drupal Core is doing can be helpful in using Drupal no matter if you are just working with modules as a site builder or you get under the hood as a developer.

##  Information Types

In addition to the "parts" of a CMS being the front-end, the back-end, and the database, there are different ["information types" in Drupal.](https://api.drupal.org/api/drupal/core%21core.api.php/group/info_types/10)  The information types might be thought of cutting across all the parts but where an understanding of them is very valuable is between the back-end and the database.  The basic information types in Drupal are:

-  Content
-  Session
-  State
-  Configuration

The [Session information,](https://www.drupal.org/project/session_api) being things like is someone logged in, can be used in how you design or run your system.  This is especially true with things like ['Permissions by Role'](https://www.drupal.org/docs/7/understanding-drupal/users-permissions-and-roles) which Drupal is known to have extraordinarily effective management of in how it works.  Think about what you might show to an anonymous user versus a logged in user, verses a premium paying users, versus editors, and developers; all under your control.   And if what is in Core isn't enough there are contributed modules that take things even further with [Groups or what might be thought of as Departments in your organization.](https://www.drupal.org/project/group)

[State information]( https://www.drupal.org/docs/8/api/state-api/overview) can be thought of as more mechanical stuff the system itself generates.  Not as likely to be directly used in things you may do unless you are a developer.  Think of it often valuable in relating to 'time'; like when the the cache last updated or [CRON](https://www.drupal.org/docs/administering-a-drupal-site/cron-automated-tasks/cron-automated-tasks-overview) last run. 


[Configuration information](https://www.drupal.org/docs/drupal-apis/configuration-api) is something you care a lot about.  What will happen if you don't do anything with importing and exporting configurations, the work you do in setting things the way you want them as you get started will disappear.  I don't mean your Drupal installation will be gone.  Rather, things like the name you set, the theme change you made, the logo you applied, those will revert back to the default starting point because you didn't really save them.  The basics of saving your configuration are simply to think that what you have done [doesn't get saved until it gets converted into files, something called YML formats, and those making their way into the database](https://www.youtube.com/watch?v=s46oXPDsJ3M)   If you are [using the Continuous Integration and Continuous Development Base Project we provide this configuration management process is set up across our multi-environment workflow.] (../cicd/configatroot.md#you-care-about-this-one-now)

## Content Information Type
