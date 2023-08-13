
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


<img src="../cicd/captures/Stopsign.png"  width="250">

<font size=5 color=red>Clone vs Explain Branch Point</font>

The explanation of how this CI/CD Workflow Project is 'built' has been consistent with what you would do to 'use it'.  It mostly focuses on setting up your computer and work environment.  To use the project, you'll [clone it from GitHub and integrate it with the Drupal template you got from Platform.sh.](../cicd/howtouseit.md)  The rest of the page below continues to explain the underlying components of the clone.  If you want to customize your workflow or manage tools within different environments (develop, staged, main), understanding that underlying detail may be helpful.

## Just Clone & Use

[Go Here!](../cicd/howtouseit.md)


## How put together, continued

If you have your project integrated between these platforms what else is there? Much of what you have done so far isn’t far from using standard Plaform.sh as a GitOps host. It wouldn’t be surprising that a relatively experienced person would do most of what was outlined as second nature.  The next items are what sets up a real CI/CD Workflow with its key components.  Things like tweaking development configuration with tools you wouldn't want in production, including automatic environment indicator names and color bars so you avoid getting lost, and setting limited but visually informative connections to database stored content to speed development performance while showing real world context.  

5) We pay special attention to assuring our `.gitignore`  file recommendations support unique CI/CD Workflow project's needs.  We put the project under 'Git' control.  However, if you are already familiar with Git, <font size="3" color=red>don't do an `init` command just yet.</font>  First, you need to [make sure you have our `.gitignore` file.](../cicd/gitignore.md)   A huge advantage of Drupal being under Composer version control coordination is that our `composer.json` file acts as a recipe to a huge amount of what is needed within the project.  This means that you avoid having thousands of files flowing unnecessarily between your local machine and a GitHub repository or Platform.sh host environment; rather the recipe is all that needs to be passed for these updates.  There are other things our `.gitignore` file excludes like log files, some IDE or sass generated intermediary files.   After we craft the `.gitignore` file, we include it as part of the the respository that can just be cloned as one starts any new project with the CI/CD Workflow Project template.  After that `'.gitigore` file is crafted, you should be save to run a `git init`; and we did that as our template was first made.
 
6) [Make it 'YOUR Project'.](../cicd/cruisevscode.md#put-your-project-into-github)  Remember, to this point your really just have a basic Platform.sh Drupal template working on that host and a copy of it on your local machine.  Sure you tweaked the `.gitignore` file but even that was just done on the local copy and isn't on Platform.sh nor in a GitHub repository.  Since you set up a GitHub account as part of the prerequisites, you need to connect the local copy, now with your `.gitignore` edits, to <font color=yellow>YOUR</font> Project in that respository.  Since you are using VSCode you can hit `shift-command-P` to bring up the command pallet and start typing `Publish to GitHub`.  With the 'extensions' we added to VSCode and our SSH connection, it should ask you if you want to 'allow' a sign-in to GitHub and back at the command pallet just start typing the name of your project (if you only have the one project and your using the VSCode IDE is the directory with your project name it likely is already in the box).  Below the box is an option that says `Publish to GitHub private repository` or `Publish to GitHub public repository` and the name of your GitHub account followed by the project name. Select and go.  <font color=yellow> Now you have integrated your project between GitHub, Platform.sh, and your local machine Lando container.</font>

<br>
[make sure you have the write and timeout settings in place and to the Drupal core update](../cicd/basebeforesplit.md#quick-lookup)*********

What you will see if you jump to our [Mid-Point Update in the detailed documentation](../cicd/midpoint.md) is an outline of the logic behind using a 'develop', 'staged', and 'main' (production) environment.  This is where the CI/CD Workflow is coming into play.  'develop' is where you do your work on a local copy linked to its host counterpart with frequent syncronization using standard 'Git' commands (from your VSCode IDE or directly from its command line).  The next step of steps that the detailed documentation describes if you need to check something, is about how the 'Drupal configuration' is managed between these different environments, how you may put certain types of Drupal modules only in certain environments, how you are aided in knowing where you are with an Environment Indicator what titles and color codes environments to help you avoid errors, how a Structure Sync and Stage File Proxy modules inclusion avoids large and potentially slow database calls during development yet maintains real-world content context for you to see while working.

<font size="4" color=Emerald>These goodies make it much safer building your website</font><br> 

Safer?  I don't know about you, but even while I am just deep into a practice situation with where I have invested a lot of effort, I hate it when I mess up and have to totally start back over.  By having copies in different environments, and controls on workflow to make sure I test before moving something I just built to what I am sharing with the world, I feel way, way safer.  GitHub, Platform.sh with its backup procedures, plus our CI/CD Workflow controls,  are strong solutions to an enjoyable experience. 

----------------------------------------------------------------------------------

7) [Bring it up to date.](../cicd/basebeforesplit.md#get-things-updated-first)  So you have the basic CI/CD Project Drupal site in place by cloning it and then doing the integration between the local machine, GitHub, and the Platform.sh host.  You can open the Drupal project and drive around in it; most likely on your local environment copy.  When you do, you will possibly find it warning you that an update exists.  If you don't know Drupal yet, this warning exists lots of times and it is NOT mandatory that you do updates.  However, with a new project it makes sense to get things as updated as possible to start.  This becomes the coordination point that [Composer](https://getcomposer.org/) uses for package management as you apply additional modules.  This includes continued coordination with the modules that are part of the CI/CD workflow.  

8) Since we updated our local environment copy, now is also a great time to [push those updates to the GitHub and Plaform.sh copies.](../cicd/basebeforesplit.md#lets-tryout-our-base-workflow)  Using our VSCode IDE we will 'stage the changes' (clicking the plus sign), click the blue bar with checkmark that says 'commit', and if all is going as we want we can click the blue bar that now says 'sync changes'.  You may get a confirming message indicating this will 'pull and push commits from and to origin/main'; that message option can be turned off so if you have done that in prior use of your VSCode IDE you may just run.  The key thing here is that the 'orgin/main' is telling you the branch environment project branch and recall we said to name your starting point as environment branch 'main' when you first established your project on Platform.sh;  this sometimes has been called 'master' by people who work with Git/GitHub with past projects.  But not only is 'main' more the modern standard, but it is also used in some of the set up specific to our CI/CD Project starting point for things to work correctly.  Our detailed documentation also has you practice your [first Platform.sh manual backup at this point.](../cicd/basebeforesplit.md#lets-do-a-Platform.sh-backup)  You see that Git 'stage', 'commit', and 'sync changes' you did updated both GitHub and Platform.sh environments; the benefit of our setting this up when signing up for Platform.sh with our GitHub account and establishing SSH and Token connections so all the environments talk to each other.


9)


  
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
