
# Content Moderation & Workflow

## In Core

Check it before you roll it out might be the simplest definition; but [Wiki takes it much further.](https://en.wikipedia.org/wiki/Content_moderation)  In that sense Drupal has an option right on the form where you are inputing your content to 'publish' or leave what you have put in as 'unpublished'.  You might think of this having a number of purposes.  You might get interrupted while doing a draft.  You might be preparing a bunch of new content to have it go out on a publication schedule.  You might have an 'overseer' like an editor, supervisor, big boss, who has to bless it before it goes out.  Heck, you might even be taking in 'user input' and have some sort of review you do before you post what they submitted.

The most current versions of Drupal have substantial [Content Moderation](https://www.drupal.org/docs/8/core/modules/content-moderation/overview) capabilities built right into it.  So your first set is just clicking the above link to make sure you know what is in Drupal Core.

If you think about the examples ways one might use content moderation, some of them might benefit from something beyond just 'published' and 'unpublished' status.  If your immediate supervisor, the section editor, the legal staff, the editor & chief, and the publisher all potentially need to review some controversial article you wrote about the town billionaire before it goes out, you probably have some sort of workflow for that process to occur.  Drupal Core also has included some powerful [Workflow Management capabilities you should review and consider.](https://www.drupal.org/docs/8/core/modules/workflows/overview)

## Modules to Enhance

We noted that you might want to move an article from 'unpublished' to 'published' at a certain date or time.  Could be to feed the beast while you are on vacation.  Could be a more complicated workflow you set up where you want to flood the boss with approvals just before deadline so you can slip more by.  Either way, you want the [Scheduler Content Moderation Integration module.](https://www.drupal.org/project/scheduler_content_moderation_integration)

If you want to trigger that flood of approvals to the boss at the last minute, you probably want to use the [Moderated Content Bulk Publish module.](https://www.drupal.org/project/moderated_content_bulk_publish)  A potentially more sane use is that you publish a newspaper with editions and want to drop all the new content into the online site at the same time that the presses release the paper version into delivery.

A tool you might like is ['drag and drop' file loading.](https://cornel.co/article/drag-and-drop-file-uploader-progressbar-wire-drupal)   Getting it is not as straightforward as just adding a Drupal module.  However, because it can be so valuable if you are grabbing a bunch of files from your photos, your local drive, an old site you are recovering content from, etc. it may be worth the extra trouble.   You have to do some coding to get it done.  But you aren't on your own.  Cornel Andreev outlines a [detailed process with all the files and code](https://cornel.co/article/drag-and-drop-file-uploader-progressbar-wire-drupal) if you want to tackle it yourself.  And, it appears he runs a development company who probably would do it for you for a fee. 

So that the boss knows that you are awaiting approval to some step in the workflow, you probably want to give the next person in the approval steps a heads up.   You will want to drop an email via integration with the [Content Moderation Notification module.](https://www.drupal.org/project/content_moderation_notifications)

You are an optimist and anticipate each reviewer will see the world just the way you do.  The last thing you enjoy is having several of them standing at your door with a printout of what you sent through the workflow steps with red, orange, purple or whatever marks each has written notes in the margin to drill you over.  Being an online person you would just as well see that 'notification' thing send you an email telling you that comments have been added to your draft via the [Moderation Note module.](https://www.drupal.org/project/moderation_note)

In your dreams there is a large truck and that nasty big boss who cuts apart your great work with those notes.  When they finally move on, regardless of how that might have occurred, their approval oversight is no long part of your workflow.  Planning ahead for the fact people move, resign, change roles, your workflow approvals are not perpetual.  Rather, you have incorporated the [Role Expiration module](https://www.drupal.org/project/role_expire) into your system to let them expire should you forget.  Wonder if you might also use it to expire your submitted work if it doesn't get approved by some anticipated publication date it logically fit with for content context?

## Roles

Content moderation is also something that is coordinated with how you set up ['Roles'.](../modules/roles.md)  You might especially like to consider the [Role Delegation module](../modules/roles.md#role-delegation-module) in coordination with your deployment of Content Moderation.

<br>
<br>
<br>

[Learn More - Drupal Modules List](../chapters.md#drupal-modules)
