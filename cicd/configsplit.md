
# SPLIT CONFIGURATION

<font color=yellow>"Active" is what's in your running project</font><br>
The easiest way to wrap your mind around configuration is to know that the ACTIVE configuration is what is in your site's database and running your Drupal site.  What doing the 'export' is accomplishing is grabbing the underlying definition of that configuration, tuning it into a whole bunch of YAML files, and putting those files somewhere outside your database.

<font color=yellow>YAML files with different 'versions' set the basis for "workflow"</font><br>
Why you want to think of it in this very basic way is that you could have different versions of your Drupal site with slightly different configurations and you could put the YAML files from those different versions into uniquely named locations.   Where this comes into play is that you have a 'main' (Production) copy of your site but you also have a copy you are working on changes and enhancements, like a 'develop' (Development) version.  Hopefully this begins to clarify how one might do a 'workflow' utilizing a sequence of copies of your website; copies from your individual local developers, individual feature builds, merged development builds, staged testing builds, in addition to your 'main' production environment.  

<font color=yellow>Enhance Configuration Management with the "Config_Split" module</font><br>
The standard Configuration synchronization in Drupal Core is great. However, it basically has just the one configuration that is ACTIVE and you are working directly against your Drupal site on any changes as you are doing additional development.  The Git/GitHub and Platform.sh/Lando approach we set up brings version control in to the picture and we want to have configurations tweaked for each environment in that workflow.   A contributed module called 'Config_Split' adds the capability to manage different Drupal environments with coordinated but slightly unique configurations.  For turning on and off certain things in 'develop', 'staged', and 'main' for the unique goals of how each is used in your workflow.

<font color=yellow>The Operating Environments for Drupal Environments</font><br>
At this point it may help to clarify that the operating environment of your Platform.sh hosted copies will contain not only the 'main' (Production) environment but also 'staged' and 'develop' environments.  So to, the Lando operating environment container on your local machine can have these three 'main', 'staged, and 'develop' environments.  In fact, at this point of building out this project workflow we have only created the 'main' operating environment container instance and a copy of it is on your Platform.sh host and on your Lando local machine.  Your Drupal project copy is in both of these 'main' operating environments.  If you haven't done anything to change the one on your local machine to update it, add or enable different modules, etc. they will be mirror images of each other.

#####<font color=yellow>Our Workflow</font><br>
Earlier we updated our .gitignore file and updated Drupal Core and Lando, showed how we use the SSH connected relationship and our Git version control commands in GitOps 'stage/commit/sync' the hosted 'main' changes to our local 'main'.  Normally we wouldn't be updating 'main' to 'main'; just in our initial set up. Our normal workflow will be to work locally on our 'develop' Drupal environment and 'stage/commit/sync' it to hosted 'develop'; then  we will [merge](https://git-scm.com/docs/git-merge) 'develop' code changes into 'staged' and conduct any testing before merging them to 'main' (Production).  If we were in a multi-developer environment or even if we were bored enough to want to jump back and forth between working on different features, we might have generated feature branches off of the 'develop'  environment and then merged upward toward main.

What we will be doing next is to set up this Config_Split in a way that allows us to have slightly tweaked Drupal configurations between our 'main', 'staged, and 'develop' plus our 'local' operating environments.  The Config_Split module will allow us to set what is working where and to set which configuration is in the "ACTIVE" state.  Since the configurations that are 'on standby' are stored in YAML files, we will set up homes for them in separate subdirectories and tell our `settings.php` where those are located.


## Summary of the next steps

- Make New Subdirectories: We need to store four slightly different copies of the YAML files that define our tweaked configurations. We will make four subdirectories adjacent to that sync location to put them in.


- Install Config_Split Module: Once we have those subdirectory locations in place we will install and enable the Config_Split module.  It will provide an additional menu item under the Administration menu right next to the Configuration Synchronization option.  In the new menu there are input boxes for you to insert the 'name', 'location', and 'configuration option choices' for each of the new configuration versions.  There is also a checkbox for 'active' that tells Drupal which of the configurations to use when and where you want.

- Define Tweaked Configurations: Initially we just set up the configuration versions.   We need to pick what we want in each.  The base template table has Site Builder, Beginning Developer, and Developer option as progressively deeper suggestions.  The default project GitHub directory is set to the Beginning Developer option; Site Builders can edit some back out and Developers can add more in.

- We Automate: Since you are trying to set up a GitOps CI/CD workflow, it isn't any fun having to go in and check which configuration box should be active and inactive each time you are marching through the process.  Therefore, we put some additional code into the `settings.php` file with conditional statements telling which configuration should be active in which branch operating environment. 

- We Avoid Confusion: It is cool to trigger the active configuration with code in the `settings.php` file.  Even more handy is detecting which branch environment we are working in to display it.  We install another Drupal contributed module that basically keeps us from doing something dumb.  Just to make sure you know which branch you are working in at any given point, we will install an indicator to make it obvious; `composer require 'drupal/environment_indicator`.





[- Next -](../cicd/configsplit2)
