
# UUIDs: Friend or Foe

#### Wonder why we only populated the one configuration subdirectory?
Although we've made progress in configuring different environments, we haven't fully implemented the variations. We created subdirectories and installed the config_split module to manage unique configurations. However, we have only filled one subdirectory with the exported `yml` files.
 
#### The reason
We didn't do those things because we aim to essentially clone all the stuff we have done as a jumpstart for new websites. Only then will be split what is at that point "your" website.  However, we can't just install a new Drupal website hosted by Platform.sh and pull the project code down from GitHub.  Yeah, crazy as it sounds, Drupal stops you from using such a clone.  When I first discovered this about Drupal I thought this must be a trick or something.  Conspiracy theories raced through my head… "Open Source my foot, now I know how they get you… bet they sell you a secret key or something".

#### The real reason
I discovered the power of UUIDs in Drupal's file structure. These unique codes, also known as [Universal Unique Identifiers,](https://en.wikipedia.org/wiki/Universally_unique_identifier) are not exclusive to Drupal. They serve as keys in databases, ensuring that your code connects to the correct database information. UUIDs prevent mistakes, like pulling from the wrong database. When working with multiple environments, such as 'local', 'develop', 'staged', and 'main', it's crucial to have the right code in the right place at the right time.  If you have multiple projects with different databases you don't want to accidentially point to the wrong one.

#### You mean Drupal hasn't dealt with cloning a starting point project?
While preventing stupid is a wonderful idea, it also creates a problem.  Drupal is aware of that problem and trying to do something about it.  Just like you and I, they agree it would be really helpful to people if they could just copy some other Drupal project and use it as your starting point.

An Initiative about [Starter Kits](https://www.drupal.org/about/core/strategic-initiatives-distributions-and-recipes) has been thrown around but it seems that the terms "Distributions and Recipes" are gaining popularity among the Drupal community, which is great. I've enjoyed joining their teams and listening to their ideas. Even if they succeed, it won't replace what we're doing here. They focus on Drupal, while we work with containers, Git Version Control, CI/CD processes, and hosting. When they launch, we can simply add some enhancements to our Composer.json file to further accelerate our project.

We're going to continue with our broader Drupal CI/CD Workflow project to create a well-crafted starting point  which can be reused repeatedly, using workarounds for the UUID issue. We're not abandoning safety as the CI/CD GitOps workflow itself is all about safety.  So we opt for our workflow management approach which then allows our starting point to be cloned pretty much in the same way as most Git Repositories.

## Introducing the Config Suite module
The approach we are going to use is to leverage a contributed module called Config Suite.  This module has a secondary intent of dealing with the UUIDs and a primary intent of automating config-export (drush cex) and config-import (drush cim) steps.  <font color=yellow>The way this module deals with the UUIDs is NOT to change them but to simply ignore them.</font>    The way that Conf Suite ignores the UUIDs is by doing a little php magic surpressing an event trigger that extends Drupal's basic configuration of "SystemConfigSubscriber": 

<img src="../cicd/captures/UUID1.png"  width="700">

There is an [appendix](../cicd/changeUUIDs.md) which offers more detail on putting a UUID back in place, if you want to, after we have Git cloned our Drupal CI/CD Workflow project into a newly installed site.

No more php lessons, just the point that the Config Suite module is important to avoid getting the error message "Site UUID in source storage does not match the target storage." Therefore we install and enable the Config Suite module with composer and drush like we have been doing with the other modules:

`lando composer require drupal/config_suite`<br>
`lando drush en config_suite`

The primary intent of the Config Suite module plays into our workflow plans too.  We have shown a number of times already how you should expect to do a 'lando drush cex' from your local version of your site to get the changes you have done during development into yml files and then commit/stage/sync them in VSCode to get those into the platform.sh hosted branch you are working from.  If you think about having to 'cex and cim' all the time, you know you will be doing it way to much.  The author of the Config Suite module [points out in a video](https://www.youtube.com/watch?v=02IJGgGPBAw&t=112s) that he got into computing because the logic is that the computer should automate stuff you do all the time.  After you install and enable the Config Suite module and go look for it in the Administration menu by your Configuration Synchronization or Configuration Split options, you will see these simple options:

<img src="../cicd/captures/UUID2.png"  width="450">

Wow... Automatic Import and Automatic Export!  How does that work?

That's what you will learn by going to the Next page.


[- Next -](../cicd/autoconfig.md)
