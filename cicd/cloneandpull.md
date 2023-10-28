
# GitClone the Project/Get the Database 

## Summary Steps

a) Git Clone the Project from GitHub<br>
b) "Lando Pull" and use spacebar to make selections<br>
c) Run "make update_project" from terminal command line<br>
d) Run "lando rebuild" from terminal command line and 'y' at prompt<br>

<font color=yellow>Takes a while to run!</font><br>

## The Details

Remember that the actual code for your project is in your GitHub repository.  Remember that we kind of tucked a few files in that repository that we really don't want the host to run but that we want to have locally to do somethings in that Lando local machine-environment; one we marked was the 'my-example.settings.local.php' file so it can be cloned down and the leading word removed to make it locally functional.

What you want to have as a starting point is your root level above where the project was/is going to be.  So if you have the project we have been working on in a directory, go a head and rename that directory with the word 'temphold' in front of the name you had. That way you can go back to it if you need but you can have GitClone bring down and tuck the retrieved project into the originally named directory.  <font color=yellow)Remember – DO NOT BE "IN" that directory, BE "ABOVE" it one level because GitClone will recreate it in the right spot that way.</font>

Remember in your VSCode IDE you hit `Shift-Cmd-P`  to bring up the "Command Palette" for the list of commands it will run for you.  Start typing `Git Clone` and it will roll to the top of the list; select it -

<img src="../cicd/captures/cloneandpull1.png"  width="350">

The selection box will show you the projects you have set up in the GitHub repository that are available for you to select.  Make sure to select the right one that matches where your Platform.sh project is running from and hit enter. 

Up will pop a list of your directories sort of like your normal 'finder' (Explorer for Windows people).  Make sure you are at the level above where you want the project clone to show up; potentially parallel then to where that 'temphold-xxxxxxxxxx' directory is showing on the directory list you see.  You don't want to point to any existing subdirectory since Git Clone is making a new one; so don't be fooled into pointing at one by the "SELECT a Repository Destination" button hinting otherwise; just hit that button without pointing at anything!

<img src="../cicd/captures/cloneandpull2.png"  width="700">

If you look in the VSCode IDE on the left hand panel, like usual that little pages symbol is on the top left and clicking it will bring your project files into view; right back home on your own machine.  Since your GitClone brought your code from GitHub to your local machine, <font color=red>follow the steps in this Lando site documentation</font> where it says "[if you already have your code locally](https://docs.lando.dev/platformsh/getting-started.html).

Before we kick off the Lando step, remember that you want to duplicate the `my-example.settings.local.php` file and rename it without the `my-example` front portion.  The easiest way to handle this is via [running the correct "make..." command;](cicd/make.md) likely `make update_project` if this is an initial local build of a hosted platform.sh project.  Just remember that after you have the project actually running locally you will then want to run `make development_project` and so a `lando rebuild` to disable some key cache settings that make development work easier.


### Steps the lando documentation outlines for existing code
<font color=yellow>NOTE: This step the documentation didn't mention but I found it important because of the larger number of files in a current version of Drupal's core and a slow connection speed for composer to get and then have time to install files.  The default composer process max timeout seemed to be 300 seconds and I jumped it to 900 because I was having some trouble. Infact, during a major update [I have set it much higher](cicd/updateproject.md#make-sure-there-is-time)</font>

`export COMPOSER_PROCESS_TIMEOUT=900`

<img src="../cicd/captures/cloneandpull3.png"  width="500">

With a step sequence, first do a `lando init \`<br>
it will prompt with just an → where you enter `--source cwd\`<br>
another →where you enter `–recipe platformsh`<br>
then it asks you to select a Platform.sh account and lists those you have; you 'arrow' to it

<img src="../cicd/captures/cloneandpull4.png"  width="500">

At that point it asks you to add or refresh a token.  Since you probably didn't save yours or it may have timed out, just go into Platform.sh, move to the upper right and select 'My Profile'

<img src="../cicd/captures/cloneandpull5.png"  width="225">

Remember that in 'My Profile' you can move your cursor to the right and select the `API Tokens` option .
Just go ahead and generate a new token and copy it -

<img src="../cicd/captures/cloneandpull6.png"  width="600">

<font color=yellow>Don't let the system fool you at the point you paste it in at the end of the line.</font> The cursor doesn't move when you paste it.  So now you think you need to try pasting it again and if you do you will get an error.  Rather, just accept the fact the cursor didn't move and hit enter.  Then you are prompted to 'arrow' to your project.

<img src="../cicd/captures/cloneandpull7.png"  width="500">

Do a `lando start`

<img src="../cicd/captures/cloneandpull8.png"  width="500">

After it runs and the list of URLs comes back, do a `lando pull -r database -m web/sites/default/files`

<img src="../cicd/captures/cloneandpull9.png"  width="500">

This will bring your database to the code you brought down from GitHub and you now how a fully functional local copy of the project running in Lando and connected to GitHub and Platform.sh

<img src="../cicd/captures/cloneandpull10.png"  width="600"><!--
--><img src="../cicd/captures/cloneandpull11.png"  width="600">

Run a `lando info` and you should see the URLs for your running local project plus stuff about it. It should look something like this -

<img src="../cicd/captures/cloneandpull12.png"  width="500">

You can copy one of those URL addresses, go over to your browser, paste it in the address box at the top, hit enter and you should see your running website ('local' environment copy).


[- Next -](../cicd/make.md)

