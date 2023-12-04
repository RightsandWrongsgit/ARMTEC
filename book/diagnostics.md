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
on missions [you might review this](https://kb.iu.edu/d/abdb).

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
