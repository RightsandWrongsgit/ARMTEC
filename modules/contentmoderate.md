
# Content Moderation & Workflow

## Your Plan

The simplest definition of Content Management might be Drupal's option to 'publish' or leave what you have put in as 'unpublished' right on a content input form. [Wiki takes what Content Management should include much further.](https://en.wikipedia.org/wiki/Content_moderation)   Working just your own website you can see the value of doing a draft.  You might also like the idea of preparing a bunch of new content to send out automatically on a publication schedule.   If you have a newspaper with an immediate supervisor, the section editor, the legal staff, the editor & chief, and the publisher all potentially needing to review some controversial article you wrote about the town billionaire before it goes out, you probably see value in a Content Managed workflow.<br>

## In Core

Drupal has substantial built-in [Content Moderation](https://www.drupal.org/docs/8/core/modules/content-moderation/overview) capabilities.  It also has roles and role permissions so you could establish content contributors, editors, publisher or other types of roles and what they are allowed to do.  For publishing steps authorization before going live Drupal includes some powerful [Workflow Management capabilities you should review and consider.](https://www.drupal.org/docs/8/core/modules/workflows/overview)<br>

The [Drupal.org documentation on core content moderation](https://www.drupal.org/docs/8/core/modules/content-moderation/overview) is thus a good starting point. You might watch this video on [Content Moderation Basics.](https://www.youtube.com/watch?v=8R2qiFMU8v8)  And add in Workflows...<br>

`composer require 'drupal/workflow`<br>
`drush en workflows`

<br>

# Enhance Core

## Bulk Publishing

If you want to trigger that flood of approvals to the boss at the last minute, you probably want to use the [Moderated Content Bulk Publish module.](https://www.drupal.org/project/moderated_content_bulk_publish)  A potentially more sane use is that you publish a newspaper with editions and want to drop all the new content into the online site at the same time that the presses release the print version into delivery.

`composer require 'drupal/moderated_content_bulk_publish`<br>
`drush en moderated_content_bulk_publish`

<br>

## Moderation Notes

You are an optimist and anticipate each reviewer will see the world just the way you do.  The last thing you enjoy is having several of them standing at your door with a printout of what you sent through the workflow steps with red, orange, purple or whatever marks each has written notes in the margin to drill you over.  Being an online person you would just as well see that 'notification' thing send you an email telling you that comments have been added to your draft via the [Moderation Note module.](https://www.drupal.org/project/moderation_note)

`composer require 'drupal/moderation_note`<br>
`drush en moderation_note`

<br>


## Diff Module

Drupal maintains versions of content right from what is available in core.  But if you want to enhance a perspective on what edits and updates the various players in the content approval process have done, you may want to try the Diff Module.  For an [outline of how to do content moderation with the Diff module included, take a look at this link.](https://www.lullabot.com/articles/basics-drupal-revisions-and-content-moderation)<br>

`composer require drupal/diff`<br>
`drush en diff`

<br>

## Scheduler Module

Once you have your site going, you may want to move the content from unpublished to published under a schedule. [Use the Scheduler Module.](https://www.drupal.org/project/scheduler)  Let's say you are taking a holiday and you want the site to looked refreshed while you are gone.  Just prepare content in advance and then schedule when it will be published. 

`composer require drupal/scheduler`<br>
`drush en scheduler`

<br>

## Content Moderation Sidebar

This module is something you probably don't want to bother with as a developer or site builder but when it comes time for adding and editing content you probably want it; or your content editors will.  You need to enable the basic 'content moderation' that is part of Core and then add this module to make the GUI interface a little easier for content editors to use.

`composer require 'drupal/moderation_sidebar`<br>
`drush en moderation_sidebar`

<br>

## Drag & Drop Loading

A tool you might like is ['drag and drop' file loading.](https://cornel.co/article/drag-and-drop-file-uploader-progressbar-wire-drupal)   Getting it is not as straightforward as just adding a Drupal module.  However, because it can be so valuable if you are grabbing a bunch of files from your photos, your local drive, an old site you are recovering content from, etc. it may be worth the extra trouble.   You have to do some coding to get it done.  But you aren't on your own.  Cornel Andreev outlines a [detailed process with all the files and code](https://cornel.co/article/drag-and-drop-file-uploader-progressbar-wire-drupal) if you want to tackle it yourself.  And, it appears he runs a development company who probably would do it for you for a fee.<br> 

## Content Planner System

An emerging power player is the [Content Planner module.](https://www.drupal.org/project/content_planner)  At a minimum, the developer of this module is to be complimented for one of the best module descriptions on Drupal.org.   But this little wonder is likely to get awards from anyone who has a serious need to manage content.  Imagine a Dashboard function of publication status, an integrated Google Analytics, last and pending update lists, available widgets, and links to key connections like MailChimp.  All that is just the first tab.  Then imagine a calendar function with macro view and details by day of content types (articles, newsletters, social, etc.) with titles across the weekly view.  And just jump to the next tab for the 'who', 'when', 'where' drag-and-drop which you will find extraordinary if you involve multiple players in development, placement, approvals, across your organization and a client's.  The [3-Minute demo gives you a quick understanding,](https://www.youtube.com/watch?v=8TzJZR2j_34) but don't worry about the security warning shown as the video was shot early in the release and the module is now fully good-to-go.

`composer require 'drupal/content_planner`<br>
`drush en content_planner`

<br>

## Workbench

It is worth really thinking through the approach you will take to content moderation in terms of roles involved, process control steps you want to assure quality, how notification of pending steps between people should occur, and more.  [Advanced Content Moderation in Drupal is a video that provides a good overall perspective.](https://www.youtube.com/watch?v=A5Gi8JAry8Q)  If you find you are going to have a bunch of content editors and approvers in a workflow, you might consider a streamline interface UI for these roles by using [Workbench, Workbench Moderation, Workbench Email](https://www.youtube.com/watch?v=VEUZeWOrDeo) or [Content Moderation Notifications](https://drupalize.me/tutorial/overview-workflows-and-content-moderation) contrib modules.

[Workbench](https://www.drupal.org/project/workbench)<br>

`composer require 'drupal/workbench`<br>
`drush en workbench`

<br>

[Workbench Moderation](https://www.drupal.org/project/workbench_moderation)

`composer require 'drupal/workbench_moderation`<br>
`drush en workbench_moderation`

<br>

[Workbench Email](https://www.drupal.org/project/workbench_email)

`composer require 'drupal/workbench_email`<br>
`drush en workbench_email`

<br>

[Content Moderation Notifications](https://www.drupal.org/project/content_moderation_notifications)

`composer require 'drupal/content_moderation_notifications`<br>
`drush en content_moderation_notifications`

<br>

[Workbench Access](https://www.drupal.org/project/workbench_access)
This module brings some of the People, Permissions, Role elements to Content Management.<br>

`composer require 'drupal/workbench_access`<br>
`drush en workbench_access`

<br>

# Share Content

It is pretty common that you want to share information between sites; meaning more than just the common  [links modules.](../modules/linksmodals.md)  People share data, they exchange with RSS feeds, and more; [Check here](https://www.drupal.org/node/627270) for a complete review. 

## RSS Feeds

The [Feeds module](https://www.drupal.org/project/feeds) is probably the most commonly used of the RSS capabilities of Drupal and their overview of the module points to both companion and alternative modules.

## Multiple Drupal Sites

Sometimes what you mean by sharing content isn't grabbing a feed from an external site but rather you want to take the input of your own content and present it on more than one of your own sites.  For this you will want to use the [Entity Share module.](https://www.drupal.org/project/entity_share)   For a detailed review of this module you can see a [presentation by one of its maintainers.](https://www.youtube.com/watch?v=RSB1pXPD3v4)

# People and Permissions

Once Fields and Content Types are established, one can prepare for operating the site by establishing Roles, Role Permissions, and the Workflow around Content Moderation.
In the Administration interface, under the "People" menu, you can set Roles and then grant Permissions for what any Role you create is permitted to do.  These basics in core can be enhanced with additional contributed modules.  In core, enable content moderation...<br>

`drush en content moderation`

<br>

## Roles

Content moderation is also something that is coordinated with how you set up. ['Roles'.](../modules/roles.md)  You might especially like to consider the [Role Delegation module](../modules/roles.md#role-delegation-module) in coordination with your deployment of Content Moderation.<br>

<br>

## Role Expiration

In your dreams there is a large truck and that nasty big boss who cuts apart your great work with those notes.  When they finally move on, regardless of how that might have occurred, their approval oversight is no long part of your workflow.  Planning ahead for the fact people move, resign, change roles, your workflow approvals are not perpetual.  Rather, you have incorporated the [Role Expiration module](https://www.drupal.org/project/role_expire) into your system to let them expire should you forget. Wonder if you might also use it to expire your submitted work if it doesn't get approved by some anticipated publication date it logically fit with for content context?

`composer require drupal/role_expire`<br>
`drush en role_expire`

<br>

## Field Permissions module

With the [Field Permissions Module](https://www.drupal.org/project/field_permissions)  you can move further with the field level permissions  than you can from the admin section of Core.<br>

`composer require drupal/field_permissions`<br>
`drush en field_permissions`

<br>

Also see [using taxonomy term associations to set tight permissions on various entities.](../modules/taxonomy.md)

<br>









<br>
<br>
<br>

[Learn More - Drupal Modules List](../chapters.md#drupal-modules)
