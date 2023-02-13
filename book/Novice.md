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

## KNOWING WHERE YOU ARE -
You want to edit the .BASH_PROMPT file.  The 'dot' in front of it hints that it is a hidden file.  On a Mac you can hit CMD SHFT DOT and it will show hidden files.  Then copy
the code from this link, paste it in and save it.*  (https://raw.githubusercontent.com/mathiasbynens/dotfiles/master/.bash_prompt).  Next time you open the terminal you should
have a command prompt that shows you a colored two part prompt that indicates first what local subdirectory you are in and second where you on on GITHUB (since you probably
haven't set up and logged into GITHUB yet it probably won't show anything for the second part yet, but trust me, it will later and be very helpful).

* You edit these in a text editor and if you are using the terminal in the apple/mac/iOS system you need to make sure that editor is set up for the right formats.  That editor
will use the keyboard function setting of your operating system and those are set in your “System Preferences” “Keyboard” in an OS system.  There is a tab called “Text” in there
and a box on that tab which, if checked, using “smart quotes and dashes”… Uncheck that box or you will be screwed up because the terminal can’t use that style quote and dashes in
its commands.  

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

# DIAGNOSTICS:
Sometime when you have problems it helps to know a few diagnostic tricks.  So some are provide here to at least get you started.  You can always search for more on specific topics
if you at least get some of the basics covered.

### Check the paths -
The first thing that is often a problem is that some file isn't being found as it is needed.  You know about directories from your Finder or Explorer look around your system. But
how does one part of your system know about files in another part?  This is where PATH comes into play.  You probably saw something like export PATH="/usr/local/git/bin:$PATH"
when you looked in the .BASH_PROFILE, .BASH_RC, and/or .BASH_PROMPT examples mentioned earlier.  This is how you show one part of your system to another.  Before you go messing
around with adding or editing those, two tips: 1) at your terminal command line interface type   echo $PATH   and hit enter to see what paths are present already and 2) See those
things that look like quotation marks... we need to make sure they are  neutral, vertical, straight, or ASCII quotation marks, NOT the curly or curve kind from a word processor.

### Check the Bash file logic -
Sometimes you will get someting like   :Command not found    on your terminal when you open it even if the prompt eventually shows up and lets you continue.  But you have no idea 
what command wasn't found, where, why, etc.  What you want to do is to debug the Bash files.  to do this put these two lines at the beginning and then the third line at the end
of your Bash file, open the terminal and it will have given you a dump that you can trace where that Command not found kicked out.

`set -x			# activate debugging from here`

`w`

`set +x			# stop debugging from here`

### Check Directory Existence -
Drupal is pretty good at giving warnings during the installation process of not being able to find a directory or file.  Sometimes it is not clear if it didn't find a file because
it isn't there at all or because it can't get to it.  So when you get a warning message start by using finder, explorer, or their counterparts to look over the directories and
files.  If a directory simply isn't there, go to a subdirectory immediately over top of where the new directory you need and then type `mkdir newdirectoryname` and hit enter.

### Check Directory and File Permissions -
Most of the time a directory or file at least has 'read' permissions so you will be able to see into it; (Remember Cmd+Shft+period can be used to show hidden files on a Mac). But 
keep in mind, that there are occassion especially during something like installing, which require permissions greater than just seeing and reading a file or inside a directory.
The first thing you might want to check is to see exactly what the permission situation is on a file and you can type `ls -l directory/directory/directory/filename.fileextention`
and hit enter to find out (if already in the directory where a file is located you don't need to string out the whole directory nest where it is, just do `filename.fileextention`) Or, if you just want to see for the files in the directory location you are already in AND include hidden files, type `ls -al`.

Commonly someone might want to grant wide access to a directory during installation and type `chmod 777 directoryname` and enter to do so; thus giving read, write, and execute
permissions to 'self/group/everyone'.  You wouldn't want to leave it that way in a live website for security reasons so you would change it to a more appropriate designation then.
You might do `chmod 644 filename` to grant read-write access to the owner(you) but only read access to your group and everyone else.  Or perhaps `chmod 664 filename` to grant
read-write to you and to your group but just read access to everyone else.  If a file needs to be written to during the installation process you might `chmod 666 filename` to
grant access of read-write to self/group/everyone for something like a settings.php file but you certainly want to lock permissions down for security reasons afterward.  For more
on missions you might review (https://kb.iu.edu/d/abdb).

### Checking Git Configuration -
Sometimes you might question where Git is pulling its information and it it is set up correctly.  To see where it is pulling from run

`git config --list --show-origin`

### Copy and Paste Across Screen Shared Connection -
You will find at times you may benefit from being able to copy code from your local machine to another to which you have made a Screen Shared connection.  You have another machine
that shows up under locations in your 'Finder' and you see it listed as a location.  You have right clicked on the other machine and requested to Screen Share it.  This allows you
to look at the files on the other machine and even move from directory to directory as you browse them.  But sometimes you find a section of code that you want to copy and then
bring it over to your local machine and paste it into another file you have open there.  When you do the paste, what you thought should be in the clipboard isn't and either empty
or whatever you had last copied locally is pasted.  The copy-paste across machines doesn't seem to be working.  All you need to do is go to the machine where you have the 'Screen 
Sharing' open and move right on it's menu to the 'edit' button, pulling down the list, click on the 'Use Shared Clipboard' option and you will be all set.

### Finding the Location of your PHP.ini file -
There are a number of things that are controlled in your php.ini file and it loads so early in the process that you can't do some things in say your settings.php or your
local.settings.php file to change them.  Therefore, you may need to edit the php.ini file directly.  Some common things might be to edit the memory_limit=128M, the
upload_max_filesize=2M or the post_max_size=8M entries to increase or limit their values.  Do remember that the post_max_size should be set a little larger than the 
upload_max_filesize value unless they are very large (e.g. 100M or more) because the uploaded file likely has some additional associated context material with it.  To find the 
location of your php.ini file, at the command line type `php -i | grep php.ini`
