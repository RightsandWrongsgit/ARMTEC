
# The Environment, The Application, The Database:

## MANAGED DIFFERENCES BETWEEN DRUPAL ENVIRONMENTS:

We have talked about how using a container based approach with Platform.sh and Lando (both of which use Docker containers) is aimed at coordinating the environments upon which your applications run.  You hear people say it gets rid of the "Well it ran on my machine' issue.  We also talked about how the GitOp workflow of Platform.sh and your local development environment, e.g. Lando plus the parallel Git-GitHub version control, also aim to coordinate application consistency between the environments.  Noble goals…  Now let's talk about breaking these rules!  If you give some thought to it, there are a few situations where you intentionally DON'T WANT CONSISTENCY. 

DIFFERENCES IN THE OPERATING ENVIRONMENTS - Start this process by thinking about Platform.sh as your host being the most sane controller of the most critical environment; 'main' (Production).  Then think about the three YAML files that Platform.sh installed in our project which control the definition of the Production environment for your project. 

image

Initially, you may not be messing with these files but as your project develops further you may find some reasons too.  Some examples of what might be added to these may be an email system to run on the production site or some performance diagnostics that make sense on 'main' (Production) but not on 'develop' (Development) environments.  

If you are working on a new project, one that doesn't have any unique environment additions set, then Lando for your local 'develop' (Development) environment is pretty much going to just inherit the basic platform.sh 'main' (Production) environment settings.  The easiest way to understand this may be to take a look at your .lando.yml file.  It probably looks as simple as this: 

code image

That is saying to use the same images and configuration mechanisms locally as platform.sh does in Production.  That means it is also using the information from the services.yaml and routes.yaml that were set up in your Platformsh subdirectory.  And, Lando spins up the same things you have in your .platform.app.yaml file for build flavor, dependencies, deploy hooks (think triggered actions), set up relationships/variables/web configuration/cron tasks.  

Well if this is all the same, why does that .lando.yml file even exist?  Because in your real world, you are going to have something in that 'overrides:' section telling Lando you want something different in your local environment.  So what are you going to put in there?   Here is a very basic example to start from:

code image

The override is saying in an .app you have variables, one of which is the APP_ENV that you want set to 'develop' for Development.  And your app has a variable telling us it is using d8settings: which contains a variable called skip_permissions_hardening that you want set to 1 (which is TRUE).  What this is doing is turning off some security lockdowns that are in your 'main' (Production) site to protect it but that needs to be turned off in your 'develop' (Development) site so that you can actually work on it.  The db entry shows how you can even change database properties like the size of the packet it will exchange (I believe this property is 64 in Platform.sh and the above syntax is just showing a 1MB change as an example).

The example file above is the .lando.yml plug-in file from the GitHub Lando/Platformsh repository.  You can go to that repository and review the README for an express summary of a basic Platform.sh site creation followed by creating its associated Lando local counterpart.  

code link

DRUPAL IN DIFFERENT ENVIRONMENTS -  We talked briefly about how multiple environments exist with slightly unique, managed differences between 'main' (production), 'staged', and 'develop' (Development) of the same site.  Things that differ at the environment level might be having a 'cache' on in Platform.sh hosted 'main' but off in Lando local while you work; or having Google Analytics running in 'main' but not while you are testing in staged; or including a bunch of tools like Devel Generate, or CSS compliers or CSS and JS code disaggregated and the cache turned off during Lando local development.  Well some of these are environment differences and but some are actually slight differences in the Drupal application like having the Devel module enabled or not.

To understand the Drupal 'application differences' it first makes sense to understand a little more about how Drupal itself manages its 'Configuration'.  Since Drupal is a Content Management System (CMS) it will come as no surprise it has a Database element; and you also knew this from the initial set up screen when you moved through the step setting up the database.  Obviously, like any application, Drupal has Code.  We had a pretty good feel for the existence of lots of Code from the directories, sub-directories and all their files when we walked through some of the Git-GitHub discussion.  Life is NOT as simple as "Content = Database" and "Function = Code".  Drupal stores a number of key configuration files in its database.  And, importantly, it keeps representations of the application configuration in YAML files that it stores in the /sites/default/files/configwithahashcode/sync subdirectory (example below).

image

Because Drupal is a PHP application, one of its most fundamentally central files is the settings.php file which is also located in the /sites/default/files sub-directory.  If you look inside that file, typically toward the end of the file, you will see a line of code similar to this …

code

Thus, in a typical Drupal installation that line of code is telling your application where to look for the key files that define your configuration.  Without going way into it, that configuration would be things like modules, menu structure, site name, etc.  Obviously, the people who built Drupal know you would logically want to have a copy of what is defining your site configuration in more than one place; so  they arranged for you to be able to 'export' your configuration and then 'import' it to another instance.

NOTE OF KEY INTEREST ABOUT THIS CONFIGURATION STUFF – Remember how we did a Git to GitHub to Platform.sh copy of our work to that point where we updated Drupal Core and enhanced that gitignore file?  We even did a practice backup on Platform.sh.  You might thing that if you had to dig yourself out of a mess at that point you could just Clone your 'main' from GitHub into your 'main' on your Lando local copy on your hard drive and we good to go. Well sort of, but only partially.  The gitignore file changes would be there.  Even the Drupal version would be updated because it was changed in the recipe for your project in the composer.lock and composer.json files.  But when you ran Lando start, you would be prompted to run Drupal set up again and input a new user ID, password, email address, time zone, etc.  That is because we never produced a file of the site's configuration.  We will do that next.


BASIC SITE CONFIGURATION 'EXPORT' AND 'IMPORT':

Drupal supports basic configuration management mainly in the sense of sharing configuration definitions between environments.  Please be aware that the underlying YAML files which define all sorts of configuration elements are only about sharing 'THE SAME SITE' between environments and NOT using these exports to jumpstart a new site.  This is because every configuration file has a unique UUID specific to one and only one site but that might be shared across dozens of instances (e.g. globally deployed copies of your site fully synchronized as a high traffic site).

You can find the standard way that Drupal supports configuration management as part of the 'Configuration' menu in the 'Administration' portion of the developer tools in every site. In the section called 'Development' you will find an option for 'Configuration synchronization'.

image

You will find a page with options for Synchronization, Import, and Export.  Oddly, they really probably should have followed the alphabet in the order presented because you want to 'Export' the configuration of your site as the starting point.  This turns all the configuration definitions for your site into YAML files that can be copied and moved to where needed (e.g. other environments, machines, locations). 

image

Most people who use Drupal find that this configuration export-import stuff is better handled at the command line.  It is fast and it shows pretty clearly what is going on with the underlying YAML files.  This is especially true as you get into the config_split world.  So let's charge down this rabbit hole.  The first thing you need to understand is how your Drupal application points to where these configuration files are actually located; and there are a ton of files controlling everything you can think of.  To know where Drupal is going to look, go under that 'web' subdirectory, down to the 'sites' and then 'default' and find your settings.php file.  

image

Settings.php is sort of the holy grail of files in a Drupal system.  So at some point you will want to drive around in it and look through all the stuff if is doing.  But for now, shuffle on down and look for the line that says "//This is defined inside the read-only "config" directory, deployed via Git" and just below that comment line you will see a $settings line that says where the directory the configuration YAML files with read and write from.

image

Looking back at the directory list on the left part of your VSCode IDE you will see that directory near the top:

image

Go to your terminal in the lower right panel of your VSCode IDE and at the command line enter 
lando drush config-export 

image

ChaChing…  you will see all sorts of YAML files show up under that config/sync directory that the settings.php file told the system where it wanted to find the configuration files.

image

For more on Configuration Synchronization via traditional way in Drupal    →

There is a good, but long video on both basic configuration and config_split noted below.  Around 55 minutes in is the point where they show some scenarios with basic config management that demonstrate things like how a new module shows up, how there is an 'active' and 'staged' state that might allow you to back out of something you did by just doing a config-import that pulls from a staged copy that you haven't exported to.

link

Good but long Configuration Synchronization video   →

link

#### SPLIT CONFIGURATION 'EXPORT' AND 'IMPORT'
-  The easiest way to wrap your mind around configuration is to know that the ACTIVE configuration is what is in your site's database and running your Drupal site.  What doing the 'export' is accomplishing is grabbing the underlying definition of that configuration, tuning it into a whole bunch of YAML files, and putting those files somewhere outside your database. Why you want to think of it in this very basic way is that you could have different versions of your Drupal site with slightly different configurations and you could put the YAML files from those different versions into uniquely named locations.   Where this comes into play is that you have a 'main' (Production) copy of your site but you also have a copy you are working on changes and enhancements, like a 'develop' (Development) version.  Hopefully this begins to clarify how one might do a 'workflow' utilizing a sequence of copies of your website; copies from your individual local developers, individual feature builds, merged development builds, staged testing builds, in addition to 'main'.  

The standard Configuration synchronization in theDrupal Core that we discussed earlier is nice. However, it basically has just the one configuration that is ACTIVE and you are working directly against your Drupal site on any changes as you are doing additional development. You will see this if you use the 'Synchronize' tab and as you work you will see  'New' and 'Changed' section listings of all the stuff you have been doing.  You can move what you are doing in development to active with the synchronization option but you are sort of operating without a safety net of version control.  The Git/GitHub and Platform.sh/Lando approach we set up brings version control in to the picture.   A contributed module called 'Config_Split' then adds the capability to manage different Drupal environments with coordinated but slightly unique configurations.  For example, like we discussed regarding having certain things turned on and off in 'develop', 'staged', and 'main' for the unique goals of how each is used in your workflow.

At this point it may help to clarify that your Platform.sh hosted copies will contain not only the 'main' (Production) environment but also 'staged' and 'develop' environments.  Yet, so to, your Lando containers on your local machine can have these three 'main', 'staged, and 'develop' environments.  In fact, right now we have just created the 'main' environment for your Drupal container instance and a copy of it is on your Platform.sh host and on your Lando local machine.  If you haven't done anything to change the one on your local machine to update it, add or enable different modules, etc. they will be mirror images of each other.  Since we earlier updated our .gitignore file and updated Core and Lando, we also showed how we use the SSH connected relationship and our Git version control commands in GitOps to update hosted 'main' from changes we had made in local 'main'.  Normally we wouldn't be updating 'main' to 'main' but instead do local 'develop' to hosted 'develop' and then merge development code changes into 'staged' and conduct any testing on hosted 'staged' before merging them into hosted 'main' (Production).  If we were in a multi-developer environment or even if we were bored enough to want to jump back and forth between working on different features, we might have generated feature branches off of the 'develop'  environment and then merged upward toward main.





[- Next -]()


