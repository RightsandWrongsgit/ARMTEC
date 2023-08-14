
# Drupal CI/CD Workflow
## How is it put together?

The intent of the Platform.sh continuous integration and deployment with Lando repository is to use it as a 'grab and go' starting point.  The README on the repository itself aims to provide the instructions for quickly using it.  However, versions change, you might be looking use a Windows or Linux machine rather than a Mac, you may prefer to consider DDEV or Docksal instead of Lando, or for whatever reason, you may need to know the underlying details to allow you to make any adaptions.  The process behind the underpinnings of the repository and the code modification, starting modules additions, etc. are outlined in detail in this GitHub pages hosted companion site.

1) [Prerequisites](../cicd/prerequisites.md) provides a setup to assure your computer has the base tools to make things work.  It assures you have 'npm', 'homebrew', 'nodejs', 'git', and an [Integrated Development Environment (IDE)](../book/ide.md) called VSCode plus a number of its 'extensions' on your own computer.  It also includes 'Composer' and 'Docker'; however, if you already have those you may need to backpeddle a little to allow our process to automatically install the appropriate version.  Finally, we make sure you have a GitHub account and know how to SSH connect to it; and a Platform.sh account whose 'CDI' option you will need to use.   We are set up the SSH relationship between our local machine and GitHub if it doesn't already exist.  And set SSH up between GitHub and Platform.sh because for our project gets its build code.  Make sure you have Platform API tokens set too.  <font color=yellow> (It is recommended that you use your GitHub account to sign up for Platform.sh because then your SSH connection will be between your local machine, GitHub AND Platform.sh.)</font> 

2) Platform.sh is a critical foundation for you.   It is going to be the source of a ["TEMPLATE" for a Drupal CMS installation.](platformshdrupal.md)  <font color=yellow> The critical thing is matching the Drupal version for the template to our project version number you </font> [clone from GitHub.](https://github.com/RightsandWrongsgit/initial-test-of-platform-ci-with-lando)   Platform.sh does a pretty good job of making set up simple and provides good documentation.  Our documentation offers three different levels of getting you started:

  . The [Short-cut](../cicd/platformshdrupal.md#short-cut-approach) assumes you are an old hand working with web stuff.  
  . The [Regular](../cicd/platformshdrupal.md#regular-approach) offers basic guidance and a good reminder source.  
  . The [Step by Step](../cicd/platformshdrupal.md#step-by-step) is a cookbook with screen shots and detailed guidance. 
  
<font color=red>Key with any of these three options are a) remember the "name" you give your project on Platform.sh and b) make sure that the 'branch' you have on the host is named "main".</font>

<br>

3) Once up you have Drupal running on Platform.sh you [bring a copy local](../cicd/bringitlocal.md) for faster, safer work on your website.  Get into your 'user root directory' and type `platform` in the terminal command line to invoke the Platform.sh "CDI" you installed on your local machine to bring down a copy of your hosted project.  <font color=yellow>(Remember to be sitting in the directory level 'above' where your new project will be and all the files will be below that).</font>  A terminal type menu will present options on the command line and since you remember the 'name' of your project just pick it from those listed (if its your first time doing this it won't be hard because it is the only project you will see listed).  <font color=red>Pull it down but don't do anything to it (ESPECIALLY DO NOT CONFIG EXPORT IT).</font> 

4) Working with the your website on your local machine is fast and isolated from any production environment.  Here your IDE will pay dividends.  In [VSCode, point it on your harddrive to work on the local copy of your project.](vscodedrupallocal.md)  VSCode provides a view into the directory structure, shows the line-by-line of any individual files you pop into, and provides a terminal from which to run commands.  It also has Git and GitHub repository connections plus some other goodies outlined in the [extensions recommended as part of the prerequisites.](../cicd/prerequisites.md#vscode-extensions)  


<img src="../cicd/captures/Stopsign.png"  width="200">

<font size=5 color=red>Clone vs Explain Branch Point</font>

The explanation of how this CI/CD Workflow Project is 'built' has been consistent with what you would do to 'use it'.  It mostly focuses on setting up your computer and work environment.  To use the project, you'll [clone it from GitHub and integrate it with the Drupal template you got from Platform.sh.](../cicd/howtouseit.md) What you get with that clone already has what is shown next; so continuing here is optional.  The rest of the page below continues to explain the underlying components of the clone.  If you want to customize your workflow or manage tools within different environments (develop, staged, main), understanding that underlying detail may be helpful.

## Just Clone & Use

[Go Here!](../cicd/howtouseit.md)


## How put together, continued

If your project is already integrated between these platforms, what else is there to consider? While using Platform.sh as a GitOps host is a great start, there are additional steps to set up a robust CI/CD Workflow. This includes tweaking development configuration with specialized tools, such as automatic environment indicator names and color bars to prevent confusion. It also involves establishing limited but visually informative connections to database stored content, which can enhance development performance while providing real-world context. These components are crucial for a successful workflow.  

5) For our CI/CD Workflow, we make sure that our `.gitignore` file recommendations are tailored to meet its unique needs.  By putting your project under 'Git' control, you gain numerous benefits.  <font size="3" color=red>But before you jump into the 'init' command,</font> [make sure you have our `.gitignore` file.](../cicd/gitignore.md)   With Drupal using Composer, version control coordination via our composer.json file serves as a handy recipe for everything your project requires. This prevents unnecessary transfer of thousands of files between your local machine, GitHub repository, and Platform.sh host environment. Our `.gitignore` file avoids transfering files the recipe covers and also excludes log files, IDE or sass generated intermediary files, and more. Once the `.gitignore` file is in place on your local Drupal copy, the CI/CD Workflow Project is ready to be placed into your GitHub repository. Now, feel free to run 'git init' and enjoy the benefits. 
 
6) Congratulations on getting your basic Platform.sh Drupal template up and running on your host and local machine! Now it's time to make your local copy, with your `.gitignore` edits, truly ["YOUR" Project in your GitHub repository.](../cicd/cruisevscode.md#put-your-project-into-github)  If you're using the recommended VSCode, simply press shift-command-P to bring up the command pallet and type `Publish to GitHub`. With the extensions we added and your SSH connection, you'll be prompted to sign in to GitHub. Then, start typing the name of your project in the command pallet and select either the public or private option to publish to your GitHub account; noting the name of your GitHub account followed by the project name.  Now, your project is integrated between GitHub, Platform.sh, and your local machine Lando container. 

7) Correct `.lando.yml` tooling is essential to make sure [Drush](../book/drush.md) will work properly.  Drush is a command line tool that allows a bunch of Drupal actions to be taken with a short-cut.  People who do a lot of work in Drupal find it essential.  Even if you just use it to do a `drush cr` to clear the cache as you work, you will find it quickly become a real time saver for certain things.  For some reason, the Platform.sh template you pull for Drupal with Lando contains drush automatically but the `.lando.yml` file that is included has the tooling within its configuration set to `service: app` and you need to edit that to say `service: drupal`.

8) The [Mid-Point Update in the detailed documentation](../cicd/midpoint.md)  outlines of the logic behind using a 'develop', 'staged', and 'main' (production) environment approach to achieve the CI/CD Workflow.   Notes is how we can use standard 'Git' commands to manage version control, rollbacks, testing, and production release.  These Git commands can be run from your VSCode IDE or directly from its terminal command line.  Also described is how 'Drupal configuration' is managed between these different environments; putting certain  Drupal modules only in certain environments.

9) <font color=yellow>DON'T SPLIT IT YET!</font> We are heading toward those additional named environments beyond 'main'.  Before going there, first we want to [bring "YOUR" project up-to-date.](../cicd/basebeforesplit.md#get-things-updated-first)  So you have the basic CI/CD Project Drupal site in place by cloning it and then doing the integration between the local machine, GitHub, and the Platform.sh host.  You can open your Drupal project and you will most likely find it warning you that an update exists.  If you don't know Drupal yet, this warning exists lots of times and it is <font color=yellow>NOT mandatory that you do updates.</font>  However, with a new project it makes sense for the cleanest starting point.  Using our VSCode IDE we will 'stage the changes' (clicking the plus sign), click the blue bar with checkmark that says 'commit', and if all is going as we want we can click the blue bar that now says 'sync changes'.  You may get a confirming message indicating this will 'pull and push commits from and to origin/main'; that message option can be turned off so if you have done that in prior use of your VSCode IDE you may just run.  The key thing here is that the 'orgin/main' is telling you the branch environment project branch and recall we named our starting point environment branch 'main' when first establishing the project on Platform.sh.  Sometimes people who have worked with Git/GitHub in the past called it 'master'.  But not only is 'main' the modern standard, it is also is key you use 'main' for the CI/CD Project to work correctly.  You may as well [run a Platform.sh backup on you host at this point too.](../cicd/basebeforesplit.md#lets-do-a-Platform.sh-backup)

<font color=yellow>*******</font><br>

[make sure you have the write and timeout settings in place and to the Drupal core update](../cicd/basebeforesplit.md#quick-lookup)<br>

<font color=yellow>*********</font>

10) It made sense to push "YOUR" fresh project code and to back up Platform.sh because local, GitHub, and Platform.sh are all talking to each other by your signing up for Platform.sh with our GitHub account and establishing SSH and Token connections so all the environments talk to each other.  The detailed documentation moves to showing the [typical directory structure of a Drupal project.](../cicd/directorymap.md)  While this is benefical generally so you better understand how Drupal works, it is also an introduction into the where and how of Drupal modules.  Drupal core comes with a bunch of standard modules and you got those from the Plaform.sh template Lando Drupal installation.  Where the real strength of Drupal comes from is the huge number of additional capabilities that can be achieved by [adding on other modules.](../modules/modulesoverview.md)  This includes some key module additions that are part of the CI/CD workflow. The most basic allows [configuration splits](../cicd/configsplit.md) so development tools are separated from your live site and analytics aren't running in the middle of development.  An [Environment Indicator](../cicd/envindicator.md) provides titles and color codes each environment to help you avoid acting in errors in the wrong place.  The [Structure Sync module](../cicd/structuresync.md) better coordinates configuration between code and the database.  The [Stage File Proxy module](../cicd/stagefileproxy.md) avoids large and potentially slow database calls during development while still giving you real-world content context while working on your site.

----------------------------------------------------------------------------------
<font size="4" color=Emerald>These goodies make it much safer building your website</font><br> 

Safer?  I don't know about you, but even while I am just deep into a practice situation where I have invested a lot of effort, I hate it when I mess up and have to totally start over.  Having copies in different environments, and controls on workflow to make sure I test before moving a new something to share with the world, I feel safer with the controlled workflow.  GitHub, Platform.sh with its backup procedures, plus our CI/CD Workflow controls, are strong solutions to an enjoyable experience. 

----------------------------------------------------------------------------------



  
  • Your local 'new' project now has all it needs; sort of.  It actually has one thing extra and that is the UUID of the new project that is in conflict with the one in the 'base' project.  So we will now deal with that.
  
         ◦ First we are going to find the 'new' project UUID and copy it to our clipboard
         
         ◦ Next we are going to go in the /config/sync subdirectory of out Lando copy of the 'base' project we GitCloned locally and find the files with UUIDs.  You will edit those files by replacing the old UUID values with the one from the 'new' project instance; you probably are just going to paste over the old value from what you hopefully saved in your clipboard.
         
        ◦ Save your work locally in VSCode.  Do a lando drush cim to import the files from the /config/sync directory into the local 'active' Drupal project.  If all goes as planned, you should have no error for mismatched UUID and things should update.
        
        ◦ Having the right stuff where it belongs isn't the end of things, remember that besides those /config/sync files you GitCloned, a bunch of other stuff is different, especially the composer.json file that actually builds the Drupal Project.  So run a lando rebuild and after it runs grab one of the URLs, paste it in your browser and bring up the now 'new-but-base-configured' Drupal project.  Drive around in it for a while and check things out.
        
        ◦ Back in your VSCode IDE go to the Git symbol which by now should have a fairly high number for the files added and changed by the GitClone you did.  Select it, do your commit with "message", stage and sync.  This should put the updated local project into the 'new projects name' GitHub repository and a minute or two later you can go over to Platform.sh to see that the project has also rebuilt there.  Go look at it on the web at the project URL it shows (that is likely still the development URL for the 'main' branch since you have neither assigned an actual DNS nor branched your project yet for CI/CD workflow).  Again, check this web version and since the environment_indicator is part of our 'base' project modules and it was configured by our settings.php commands to detect and point to the right "case" in our test syntax, it should show up with a different color bar, bar label, and even favicon color. 

***********
Needed: a GitHub Read.me Summary
***********

<br>
<br>
<br>

[- Next -](../cicd/prerequisites.md)
