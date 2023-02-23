
## Our Drupal Code is Local
# Let's Take Advantage of VSCode

[VSCode](../book/ide.md) will become our coordination point for all of this.  It will give us a view of the directories of the local project, a view into the individual files we open, and through its extensions it will help do the Git/GitHub stuff.  VSCode also offers a Terminal to run things and we could go directly there to do the first step in setting up this coordination.  However, lets do it this first time with the Terminal to use the [Command Line](../book/cheats.md#Terminal-Command-Line-Interface-(CLI)) that is available right from the utlities on your basic machine.  Go into Finder and in your Applications area, look toward the bottom of your list for Utilities.  Open Utilities and toward the bottom of it, look for Terminal and click it to open.

VSCode will become your go to place while working on your website. This is because you can see your directory structure, your files, a terminal command, do git/github actions, and much more from an integrated development view.  We will just start by seeing where that local copy of your website project is located and then how you can use a terminal right from within the same tool. Remember, a local copy of the Platform.sh hosted 'main' branch is brought down with the Platform Command Line in the [process outlined at the end of the prior step](../cicd/bringitlocal.md).

<img src="../cicd/captures/vscodelocaldrupal1.png"  width="450">


See that 'Start' section in the middle of the page and go click on the 'Open' option.

<img src="../cicd/captures/vscodelocaldrupal2.png"  width="250">

You should see a 'Finder' like view where you will see the sub-directory with the name you cloned the project from Platform.sh into on your local hard-drive.

<img src="../cicd/captures/vscodelocaldrupal3.png"  width="325">

When you click on that sub-directory, you will find the project, a whole bunch of lower level sub-directories under it, and a lot of files for your project ready and waiting for you.

<img src="../cicd/captures/vscodelocaldrupal4.png"  width="450">

If you look in the very top level menu bar of your screen you will see all sorts of options for VSCode and one of those is 'Terminal'.   Select that and the first option is 'New Terminal'; which you pick and the lower right quarter of your screen opens into a terminal. 

<img src="../cicd/captures/vscodelocaldrupal5.png"  width="450">

You should see a command line in that terminal area of the VSCode screen.  It lists 'who you are', 'what machine you are on', and following the word 'in' should be the name of the directory you put your local project. Notice that what we did on [Where am I](../book/WhereAmI.md) even works within VSCode.   Thus you are pointing at the local copy of your project, seeing the subdirectories on the left, and looking inside any open files in the upper right section.  Please, even if you think you know how to use Lando, <font color=red>DON'T Do a 'lando init' yet:</font> from that open terminal. You are going to run that command in a moment but first we need to do a few things: 
  
  [Next](../cicd/gitignore.md#Do-more-with-.gitignore




