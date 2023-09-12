
# Drupal CI/CD Start Point

This should be viewed as your 'Quick Start' to setting up a Drupal hosted website pre-configured to follow basic [CI/CD Workflow principles.](../book/drupalcicd.md#what-is-cicd)  There is a complete documentation outline on [how all this is put together which you can move through page-by-page.](cicdoverview.md)  But here you are just going to be given the most basic of steps to simply dive right in.

## The Basics

Try and confirm that this works, and if so, clean this up to be almost as simply outlined with minimal narrative:

- Make sure you have steps 1 to 4 of the overview done.  This gets your accounts set up, your computer configured, and the connections between things in place.

- Clone the CI/CD Workflow Project and integrate it into the generic Drupal install the set up steps put in place.

- Add and run locally the UUID restoration module, disable the UUID ignore module

- Git init the local project and push it, under your own project name, to the GitHub or other repository of your choice

- Follow standard Git procedures to first create the 'staged' environment off of 'main', and the 'develop' environment off of 'staged' so your local Lando environment is dynanamically sync'ed with the Platform.sh hosted 'develop' environment.

- Work using standard Git processes in VSCode to work on your website.

- Use Platform.sh to move a 'develop' you are satisfied with to the 'staged' environment where you will then do any testing before moving it to 'main'

- Publish 'main' to a URL you own using Platform.sh standard DNS management procedures



********************************  NOTES THAT MIGHT ELABORATE THE ABOVE STEPS  ***********************

Once your basic computer is set up with the foundations noted, you are going to sign up with [Platform.sh](https://platform.sh/) as a hosting company.  It offers several key things relative to this project.  First, it is an experienced host of Drupal in a [container](https://code.visualstudio.com/docs/devcontainers/containers) type of environment; this includes the fact they offer a Drupal template with a good portion of what you need.  Second, it already uses a GitOps capability that leverages basic [Git](../book/gitbasics.md) based commands for its [multi-environment](configatroot.md#drupal-environments) workflow plus concurrent code backup within a [Git Repository.](../book/gitbasics.md#git-repository)  Third, they are reasonably priced, especially in the way they offer development accounts at a substantial discount before you go live.  <font color=yellow> THE KEY THING YOU NEED TO PAY ATTENTION TO IS THE VERY SPECIFIC DRUPAL VERSION OF THE TEMPLATE YOU BRING DOWN TO START WITH!</font>

You are going to mirror the host environment on your local machine with a [Lando](../book/lando.html) container; thus why you need [Lando installed, ideally Globally.]  The Lando install should have been part of what you set up as the foundation for your basic machine.

You need to be careful with the Git step in this quick start.  <font color=yellow> Don't do a "Git Init" on the project until instructed in the sequence below.</font>  What you are going to do is you will look at the [GitHub Repository for this Drupal CI/CD Project in the Composer.json file](https://github.com/RightsandWrongsgit/initial-test-of-platform-ci-with-lando/blob/main/composer.json) and look for a line under the 'require' section (typically near the top) for a line that says <font color=green>  "drupal/core-recommended": "^xx.x", </font>  and see what numbers are in the "xx.x".  The plan is that those should match the Drupal version you grabbed from the Platform.sh template you loaded.  If I am running behind the current Platform.sh template, drop me a note on GitHub to get my act together and update the GitHub repository.  Basically, all you need to do is to [clone this GitHub Repository to your local machine where Lando will be able to run it](cloneandpull.md) in its container.

However, before you kick off the Lando step, remember that you want to duplicate the my-example.settings.local.php file you pulling from the clone and rename it without the my-example front portion. The easiest thing to do is first remove the existing settings.local.php file that the GitHub project would have had in it from the Drupal scaffold; then it won’t be in the way of your renaming the copy you are replacing it with.

Now you can move into the top level directory where you brought the project into on you local machine and do a "Lando Init" on the project.  

*****  NOTE -  Need to specfy when to Git Init this*******



### Foundation

We are going to make sure our local machine is set up like [outlined in the first part of the documentation.](prerequisites.md)  If you are a relative novice, you might first want to look at our [even more core basics](/book/Novice.md#setting-up-your-basic-system) to make sure you have those in place.

IDE: VSCode & Extentions
Git
Git Respository: GitHub
  - We are going to make sure we have a GitHub account



### The host
    
  - We are going to make sure we have a Platform.sh account to work with; even if it is just the free trial one that we can convert if we like it.  And when offered how we want to log into Platform.sh we are going to chose to do it with our GitHub account.

  - We are going to do the Platform.sh template install of Drupal SELECTING THE SAME DRUPAL VERSION THAT IS NOTED IN THE GITHUB DIRECTORY FOR THIS BASE PROJECT.  And we will just follow the prompts from the template, including giving our project its new name.  Install the Platform.sh CLI (remember this is [done with homebrew and you want it globally installed because you will likely have multiple projects](bringitlocal.md) at least the branches on Platform.sh that you might pull locally at some point)
        
### The local

In the mean time, here is what we are going to do in a nutshell; followed by a deeper explanation and 'how to':


  - Install Lando (Ideally have done this globally as part of your local machine set up because you will likely use it on other projects as well)

  - We are going to go on your local machine to the directory we want to install the local version of our project (Think sitting in the level 'above'  your new project because your project will be a directory within that level and all the files will be below it).  

  - We are going to set up the SSH relationship between our local machine and GitHub if it doesn't already exist.  And we are going to set it up between GitHub and Platform.sh because that is how our project gets its build code.  Make sure you have API tokens set too.

  - Now that we have a 'new' Drupal project running on Platform.sh we pull it into Lando as a starting point.   That is a "connect" Drupal instance but it is NOT our desired "capable" base instance with all the CI/CD goodies.

  - We go to our local Lando 'new' Drupal project in our VSCode editor and park ourselves at the top level in the left panel showing the directory structure.  Do a "Command-P" to bring up the command bar and start typing GitClone and then point it to the capable' base' project that has all the good code we want be bring it.  Pull it down but don't do anything to it (ESPECIALLY DO NOT CONFIG EXPORT IT).  

  - Your local 'new' project now has all it needs; sort of.  It actually has one thing extra and that is the UUID of the new project that is in conflict with the one in the 'base' project.  So we will now deal with that.  
        ◦ First we are going to find the 'new' project UUID and copy it to our clipboard
        ◦ Next we are going to go in the /config/sync subdirectory of out Lando copy of the 'base' project we GitCloned locally and find the files with UUIDs.  You will edit those files by replacing the old UUID values with the one from the 'new' project instance; you probably are just going to paste over the old value from what you hopefully saved in your clipboard.
        ◦ Save your work locally in VSCode.  Do a lando drush cim to import the files from the /config/sync directory into the local 'active' Drupal project.  If all goes as planned, you should have no error for mismatched UUID and things should update.
        ◦ Having the right stuff where it belongs isn't the end of things, remember that besides those /config/sync files you GitCloned, a bunch of other stuff is different, especially the composer.json file that actually builds the Drupal Project.  So run a lando rebuild and after it runs grab one of the URLs, paste it in your browser and bring up the now 'new-but-base-configured' Drupal project.  Drive around in it for a while and check things out. 
        ◦ Back in your VSCode IDE go to the Git symbol which by now should have a fairly high number for the files added and changed by the GitClone you did.  Select it, do your commit with "message", stage and sync.  This should put the updated local project into the 'new projects name' GitHub repository and a minute or two later you can go over to Platform.sh to see that the project has also rebuilt there.  Go look at it on the web at the project URL it shows (that is likely still the development URL for the 'main' branch since you have neither assigned an actual DNS nor branched your project yet for CI/CD workflow).  Again, check this web version and since the environment_indicator is part of our 'base' project modules and it was configured by our settings.php commands to detect and point to the right "case" in our test syntax, it should show up with a different color bar, bar label, and even favicon color. 


*******************************************************************
## Merge, Test, Launch
*******************************************************************

### Merge 'develop' into 'staged'
Say our have been working back and forth with you Lando 'local' and Platform.sh 'develop' branches doing saves, commits, and syncs as you work.  You have done your first level practical testing by driving around in your Platform.sh hosted 'develop' branch and things look great.  Since that 'develop' branch was cloned from your 'staged' branch you want to move the change up one level so you can carry out your formal testing on the 'hosted' staged branch.  

Go down to the lower left corner of your VSCode IDE and click on the branch name; probably 'develop' since that is what you just said you were happy with.  When you click, the command bar at the top should show up and now you want to click 'staged' (the basic one, not the longer named 'origin/staged' one.  Now you should see this in that lower left corner.<br>
<img src="../cicd/captures/gitmergeup1.png"  width="250">

Go to the line in the left panel that says "SOURCE CONTROL" and click on the three dots on the right end of that line.  An option pull down list should appear and you will move down it to the <font color=yellow>Branch</font> option.  From the sublist that appears, select the <font color=yellow>Merge Branch</font> option.<br>
<img src="../cicd/captures/gitmergeup2.png"  width="400">

That will open the command bar at the top with a message to "Select a branch to merge <font color=HotPink>from</font> 
<img src="../cicd/captures/gitmergeup3.png"  width="350">

You enter <font color=yellow>'develop'</font> in that box because you want to grab all your fine development work and bring it into the 'stage' environment for final testing.

### Do your testing

### Merge 'staged' into 'main'

Go into the 'main' branch in your VSCode IDE. The lower left indicator should look like this.<br>
<img src="../cicd/captures/gitmergeup4.png"  width="250">

Go to the line in the left panel that says "SOURCE CONTROL" and click on the three dots on the right end of that line.  An option pull down list should appear and you will move down it to the <font color=yellow>Branch</font> option.  From the sublist that appears, select the <font color=yellow>Merge Branch</font> option.<br>
<img src="../cicd/captures/gitmergeup2.png"  width="400">

That will open the command bar at the top with a message to "Select a branch to merge <font color=HotPink>from</font> 
<img src="../cicd/captures/gitmergeup3.png"  width="350">

You enter <font color=yellow>'staged'</font> in that box because you want to grab all your fully tested work and bring it into the 'main' production environment and bring it live to the world.

