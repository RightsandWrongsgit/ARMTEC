
# VSCode coordination of Platform.sh, Lando, and Git/GitHub

We have a basic installation of Drupal running on our Platform.sh host.  It has a sole branch called 'main'.   We want to bring a copy of this to our local computer where we will run it in [Lando](../book/lando.md).  We will also want to put that 'local' copy of our Drupal project under [Git](../book/gitbasics.md) version control.  And we will want our Git local version control to speak to a GitHub repository.

[VSCode](../book/ide.md) will become our coordination point for all of this.  It will give us a view of the directories of the local project, a view into the individual files we open, and through its extensions it will help do the Git/GitHub stuff.  VSCode also offers a Terminal to run things and we could go directly there to do the first step in setting up this coordination.  However, lets do it this first time with the Terminal that is available right from the utlities on your basic machine.  Go into Finder and in your Applications area, look toward the bottom of your list for Utilities.  Open Utilities and toward the bottom of it, look for Terminal and click it to open.

