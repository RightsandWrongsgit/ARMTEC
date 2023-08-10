
# Drupal Workflow
## How is it put together?

The intent of the Platform.sh continuous integration and deployment with Lando repository is to use it as a 'grab and go' starting point.  The README on the repository itself aims to provide the instructions for quickly using it.  However, as versions change, as you might be looking to start from a Windows or Linux machine rather than a Mac, as you prefer to consider DDEV or Docksal instead of Lando, you may need to know the underlying details so you can make any adaptions.  The process behind the underpinnings of the repository and the code modification, starting modules additions, etc. are outlined in detail in this GitHub pages hosted companion site.

1) [Prerequisites](../cicd/prerequisites.md) provides a setup to assure your computer has the base tools to make things work.  It assures you have 'npm', 'homebrew', 'nodejs', 'git', and an [Integrated Development Environment (IDE)](../book/ide.md) called VSCode plus a number of its 'extensions' on your own computer.  It also includes 'Composer' and 'Docker'; however, here if you do have those you might have to backpeddle a little because you want the next step to automatically install the appropriate version.  Finally, it is going to make sure you have a GitHub account and know how to SSH connect to it; and a Platform.sh account for which you will also make sure you have its 'CDI' option installed on your machine <font color=yellow> (It is recommended that you use your GitHub account to sign up for Platform.sh because then your SSH connection will be between your local machine, GitHub AND Platform.sh.)</font> 

2) Platform.sh is a critical foundation for you.   It is going to be the source of a ["TEMPLATE" for a Drupal CMS installation.](platformshdrupal.md)  <font color=yellow> The critical thing is matching the Drupal version for the template to our project version number you will </font> [clone from GitHub.](https://github.com/RightsandWrongsgit/initial-test-of-platform-ci-with-lando)   Platform.sh does a pretty good job of making set up simple and providing good documentation.  Our documentation offers three different levels of getting you started:

  . The [Short-cut](../cicd/platformshdrupal.md#short-cut-approach) assumes you are an old hand working with web stuff.  
  . The [Regular](../cicd/platformshdrupal.md#regular-approach) offers basic guidance and a good reminder source.  
  . The [Step by Step](../cicd/platformshdrupal.md#step-by-step) is a cookbook with screen shots and detailed guidance. 
  
<font color=red>Key with any of these three options are a) remember the 'name' you give your project on Platform.sh and b) make sure that the 'branch' you have on the host is named 'main'.</font>

<br>

3) You want to [bring it local.](../cicd/bringitlocal.md)  This is where you leverage the fact you installed the Platform.sh CDI on your local machine.  You want to be located at your 'user root directory' when you type `platform` in the terminal command line to invoke the CDI to bring a copy of the hosted project to your local computer.  A terminal type menu will present the options on the command line and since you remember the 'name' of your project you will pick it from those listed (if its your first time doing this it won't be hard because it is the only project you will see listed).
 
4) Working with the your website on your local machine is fast and isolated from any production environment.  Here your IDE will pay dividends.  In [VSCode, point it on your harddrive to work on the local copy of your project.](vscodedrupallocal.md)  VSCode provides a view into the directory structure, any individual files you pop into, and it provides a terminal from which to run commands.  It also has Git and GitHub repository connections plus some other goodies outlined in the [extensions recommended as part of the prerequisites.](../cicd/prerequisites.md#vscode-extensions)

5) You are going to bring your project under 'Git' control.  If you are already familiar with Git, don't just just to doing an `init` command.  First, we need you to [make sure you have a `.gitignore` file](../cicd/gitignore.md) that is set up in a manner to work well with this CI/CD project template.  You will `git init` only after you have that properly in place. 

6) [Make it 'YOUR Project'.](../cicd/cruisevscode.md#put-your-project-into-github)  You make think the CI/CD Project you cloned from GitHub is now yours.  But really, at this point, you have simply borrowed it. Since you set up a GitHub account as part of the prerequisites, you need to connect the local copy, now with your `.gitignore` edits, to YOUR Project in that respository.  Since you are using VSCode you can hit `shift-command-P` to bring up the command pallet and start typing `Publish to GitHub`.  With the 'extensions' we added to VSCode and our SSH connection, it should ask you if you want to 'allow' a sign-in to GitHub and back at the command pallet just start typing the name of your project (if you only have the one project and your VSCode IDE is within it the project name is likely to already be in the box).  Below the box is an option that says `Publish to GitHub private repository` or `Publish to GitHub public repository` and the name of your GitHub account followed by the project name.  <font color=yellow> So now you have integrated your project between GitHub, Platform.sh, and your local maching Lando container.</font>

<br>

## Why more? 
----------------------------------------------------------------------------------
 
If you have your project integrated between these platforms what else is there?  Much of what you have done so far isn't far from standard Plaform.sh as a GitOps host.  It wouldn't be surprising that a relatively experienced person would do most of that as second nature; perhaps only paying special attention to our `.gitignore` recommendations for things sort of unique to the cloned project's needs.

What you will see if you jump to our [Mid-Point Update in the detailed documenation](../cicd/midpoint.md) is an outline of the logic behind using a 'develop', 'staged', and 'main' (production) environment.  This is where the CI/CD Workflow is coming into play.  'develop' is where you do your work on a local copy linked to its host counterpart with frequent syncronization using standard 'Git' commands (from your VSCode IDE or directly from its command line).  The next step of steps that the detailed documentation describes if you need to check something, is about how the 'Drupal configuration' is managed between these different environments, how you may put certain types of Drupal modules only in certain environments, how you are aided in knowing where you are with an Environment Indicator what titles and color codes environments to help you avoid errors, how a Structure Sync and Stage File Proxy modules inclusion avoids large and potentially slow database calls during development yet maintains real-world content context for you to see while working.

<font size="4" color=Emerald>These goodies make it much safer building your website</font> 

Safer?  I don't know about you, but even while I am just deep into a practice situation with where I have invested a lot of effort, I hate it when I mess up and have to totally start back over.  By having copies in different environments, and controls on workflow to make sure I test before moving something I just built to what I am sharing with the world, I feel way, way safer.  GitHub, Platform.sh with its backup procedures, plus our CI/CD Workflow controls,  are strong solutions to an enjoyable experience. 

----------------------------------------------------------------------------------

7) 





Here is what we are going to do in a nutshell; followed by a deeper explanation and 'how to':

  • We are going to make sure our local machine is set up like outlined in the first part of this documentation.
  
          ◦ Install the Platform.sh CLI (remember this is done with homebrew and you want it globally installed because you will likely have multiple projects, at least branches on Platform.sh that you might pull locally at some point)
          
          ◦ Install Lando (Ideally have done this globally as part of your local machine set up because you will likely use it on other projects as well)
          
   • We are going to make sure we have a GitHub account
   
   • We are going to make sure we have a Platform.sh account to work with; even if it is just the free trial one that we can convert if we like it.  And when offered how we want to log into Platform.sh we are going to chose to do it with our GitHub account.
   
   • We are going to do the Platform.sh template install of Drupal SELECTING THE SAME DRUPAL VERSION THAT IS NOTED IN THE GITHUB DIRECTORY FOR THIS BASE PROJECT.  And we will just follow the prompts from the template, including giving our project its new name.
   
   • We are going to go on your local machine to the directory we want to install the local version of our project (Think sitting in the level 'above'  your new project because your project will be a directory within that level and all the files will be below it). 
   
   • We are going to set up the SSH relationship between our local machine and GitHub if it doesn't already exist.  And we are going to set it up between GitHub and Platform.sh because that is how our project gets its build code.  Make sure you have API tokens set too.
   
   • Now that we have a 'new' Drupal project running on Platform.sh we pull it into Lando as a starting point.   That is a "connect" Drupal instance but it is NOT our desired "capable" base instance with all the CI/CD goodies.
   
  • We go to our local Lando 'new' Drupal project in our VSCode editor and park ourselves at the top level in the left panel showing the directory structure.  Do a "Command-P" to bring up the command bar and start typing GitClone and then point it to the capable' base' project that has all the good code we want be bring it.  Pull it down but don't do anything to it (ESPECIALLY DO NOT CONFIG EXPORT IT).
  
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
