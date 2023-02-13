# NOVICE: It's 'OK' you haven't memorized this stuff!

### Somethings are pretty basic but if no one every showed you, you might need a quick reference
If you are just starting out looking at different options for building a website, sometimes it can seem pretty complex.  Often times people are used to using their computer 
with all the GUI (Graphical User Interface) applications we have come to enjoy.  But if you are going to enter the world where you are developing your own website, you are
now going to get a little underneath the covers.  Drupal is a CMS (Content Management System) that really has extraordinary capabilities to do sophisticated websites.  It has
reputation of being 'hard' and in some senses that is true if you haven't ever programmed much before.  Therefore, lots of people default to some of the very simple options 
for putting up a website with just a few pages; almost like printing several ads on different pages of a newspaper and telling on each page what page numbers to turn to if
the reader whats to see the other ads.  That's ok if you aren't interesting in changing the content to fit the site vistor or offer tools for them to explore what you are
offering, or don't want to include forums, blogs, electronic purchases, etc.  Even if you don't initially plan to use these more advance features, some people would still 
start out with a simple Drupal site just to position themselves to expand more easily as their needs grow.

The way this GitHub Drupal repository is set up, its aim is to make it much easier to get started with Drupal than many other options.  That is because it uses something 
called 'containers'; actually pretty advanced stuff in some senses but set up here to kind of partially automate your start.  The key thing about containers is that they
contain both your application (e.g. Drupal) and its operating environment (e.g. the server & tools).  That way you sort of spin up both at once for a quicker start.  That 
said, it is still a little harder than just driving around existing applications you might have on your computer.  And you will need to use things like a 'terminal' for 
'command line interface' (CLI) to the guts of your computer.  Therefore, this SUPERNOVICE section is provided to give you some guidance in the basics.  It is stuck here at
the end because many people who will use this GITHUB repository will be experienced developers who don't want to read through a bunch of stuff that they already know.

## OPERATING SYSTEMS & SHELLS -
You probably are on a Mac or Windows, possibly even Linux; these are operating systems (OS).  Other than knowing which one you are using and some occassional differences in how
you do various tasks, I won't review the details of each OS.  There are all sorts of things on places like Wikipedia that give nice overviews and histories.  But one thing
you probably should know is that each of these OS's has something called a 'Kernel' that is like a set of commands that get the computer what to do.  And you talk to the
Kernel with what is know as a 'Shell'.  Again, there are a couple different Shells but they are pretty consistent at their most basic level.  Mac is using 'zsh' but in most
regards it is just a more capable version of BASH; and BASH is generally available across operating systems (if you want to argue that, then you obviously aren't a novice, so
move on).  BASH has some files that can be edited to provide 'scripting' (or a series of commands to be run).  But for use here, all we want to do is to edit your BASH file
that manages what your command prompt looks like (that > or $ typically present when you open a terminal).  If you use a Mac you probably know that your FINDER application shows
you where files are in various directories and on Windows it is something called EXPLORER. If you have worked with those you know you often have subdirectories below 
subdirectories below subdirectories.  With FINDER OR EXPLORER you can visually see where you are when you point to a file.  But imagine you are working just from a single
line like a command prompt on a terminal and you could be lost as to where the heck you are.  Therefore, we are going to start by modifying the BASH file in a way that make
that prompt show you information.  There is something discussed later called 'GIT/GITHUB' regarding your connection to a remote computer and we want to know where the heck
we are on both our local computer and the remote computer.  So the BASH file edit outlined next does both.



## SETTING UP YOUR BASIC SYSTEM BEFORE YOU GET STARTED
### WITH THE DRUPAL DOCKER CONTAINER 

Flesh these out with more explanation or source links but basically the following (note this is MAC oriented initially, then add Linux and Windows later) ...

* Install Homebrew
* Install Git
* Obtain GitHub account
* Establish SSH Key to GitHub account
* Install Visual Studio Code (possibly via homebrew vscode option)
* Install Composer (see Drupal.org background on Composer for lots of detail: https://www.drupal.org/docs/develop/using-composer)

Add - Include a quick discussion of how to get to the parts of VSCode to invoke a terminal to issue git/github commands, to bring up the command palette (like CLI) via shift-command-p, and to install extensions (plus what key extensions will really help you get started).


