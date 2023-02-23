
#### The practical steps by example -
So we have our base Drupal 9 project with 'main' branch set up on our Platform.sh host.  We have made a local version of that project available on our own machine within a Lando supported matching container.  If we have Git installed globally, and with Platform.sh and Lando a 'GitOp' type of workflow, that local copy of the project should be under GIT version control.   Do a 'Git Status' from within your project top level directory to see if it already is.  Otherwise doing more to your .gitignore file than what comes as a standard part of the Platform.sh Lando template.  (Note: you can do these updates to your .gitignore file either way, it is just that you might have to actively remove stuff that got sent to your repository before hand.)

# Do more with .gitignore

Earlier it was noted that the standard templates we used to establish our local and hosted site initial environment had a default .gitignore file already present.  Look for it as the very top level of your project on your local machine; the same level as the composer.json and composer.lock files.  Don't be surprised there there are other .gitignore files in various subdirectories that we also automatically installed from the template; but you want to use that top one.  It should look pretty close to this:

<img src="../cicd/captures/gitignore1.png"  width="300">

That is a good start for a plain vanilla Drupal site that isn't being worked on but your site will likely use some other stuff with it that really doesn't belong in the GitHub repository.  The simplest example is something we already started to use, VSCode, and have no reason we want to push its IDE generated files to our repository.  What we want to do is change line 20 to a broader perspective of tools and then add some others under it:

`20      # Ignore IDE files`<br> 
`21      /.idea/`<br>
`22      /.vscode/`<br>
`23     *.code_workspace`<br>
`24     *.iml`<br>

Make a space line at 25, then below that lets ignore all packages required by JavaScript with:

26     `# Ignore mode modules`<br>
27      `node_modules`<br>

Space, and since we may use SASS in CSS generation we can ignore some of the files used in its debugging:

29      `# Ignore some CSS related stuff`<br>
30      ` *.css.map`<br>
31      ` *.css.map.map`<br>

Space and since we have no reason we want to push our log files to the repository:

33     ` # Ignore all log files`<br>
34     `  *.log`<br>

Finally, at the end, lets just avoid pushing up unnecessary text files by adding these:

`# Ignore default text files`<br>
			`	/CHANGELOG.txt`<br>
			`	/COPYRIGHT.txt`<br>
			`	/INSTALL*.txt`<br>
			`	/LICENSE.txt`<br>
			`	/MAINTAINERS.txt`<br>
			`	/UPGRADE.txt`<br>
			`	/README.txt`<br>
			`	sites/README.txt`<br>
			`	sites/all/modules/README.txt`<br>
			`	sites/all/themes/README.txt`<br>

Since we are storing our site content in the database at the Platform.sh host and will have a backup procedure at that host site, we don't want to be pushing potentially voluminous content to the repository and want to add these final lines:

`# Ignore path that contain user-generated content.
			`	sites/*/files`<br>
			`	sites/*/private`<br>

You should basically end up with something that looks a lot like this.  Of course if you know of other tools you might use you might add more.  If you want to make a public facing repository you might want to keep a README or a MAINTAINER text file to help people.  


<img src="../cicd/captures/gitignore1.png"  width="300">


#### Removing something you already added to a repository:
As a quick reference note, you might have done a 'git init' and pushed some files that you now wish you hadn't and plan to edit your .gitignore so they don't go up in the future.  You might try this to remove items; 'mode_modules' is the example.

`git rm -r --cached node_modules`


What does this do?<br>
<sup><sub>-r flag makes sure the command is applied recursively to all files and subdirectories in the node_modules directory</sub></sup><br>
<sup><sub>--cached makes sure we remove the files only from git index and keep them in the working directory.</sub></sup><br> 

## Now let's do that 'git init'

It is assumed you had installed the basic prerequisite of'Git' itself on your machine before you started.  While GitHub is talking to Platform.sh and Lando's recipe pull from Platform.sh has the project local, you need to make sure that the local project is talking to the GitHub and Platform.sh repositories of that project; this is where your local copy of Git comes into play.  Move into the top directory level of the project (not the lower level 'web' directory itself but the very top) and run a 'Git Init' command. You could do this my using the terminal in the lower right of your VSCode IDE or using its GUI this way:

    • Open Visual Studio Code.
    • Put your cursor in and 'click' on the top level director of your project
    • Select 'shift-command-P' and the command pallet will open
    • Start typing `git init` and you will see “Initialize Git Repository” appear in the bar; select it and let it run.


[- Next -]()
