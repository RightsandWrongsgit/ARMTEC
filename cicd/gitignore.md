
#### The practical steps by example -
So we have our base Drupal 9 project with 'main' branch set up on our Platform.sh host.  We have made a local version of that project available on our own machine within a Lando supported matching container.  If we have Git installed globally, and with Platform.sh and Lando a 'GitOp' type of workflow, that local copy of the project should be under GIT version control.   Do a 'Git Status' from within your project top level directory to see if it already is.  Otherwise doing more to your .gitignore file than what comes as a standard part of the Platform.sh Lando template.  (Note: you can do these updates to your .gitignore file either way, it is just that you might have to actively remove stuff that got sent to your repository before hand.)

# Do more with .gitignore

Earlier it was noted that the standard templates we used to establish our local and hosted site initial environment had a default .gitignore file already present.  Look for it as the very top level of your project on your local machine; the same level as the composer.json and composer.lock files.  Don't be surprised there there are other .gitignore files in various subdirectories that we also automatically installed from the template; but you want to use that top one.  It should look pretty close to this:

<img src="../cicd/captures/gitignore1.png"  width="300">








<img src="../cicd/captures/gitignore1.png"  width="300">
