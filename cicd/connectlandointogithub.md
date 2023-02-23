
# Connecting Lando into your Github Platform.sh World 

## Quick Summary
You want to connect your Drupal9 starting point project to a local development version on your own computer where it is faster to code changes you will make to the Drupal site to personalize it for your purposes.  More on adding module components, nice looking themes, and content to a Drupal site later, after we have the basic site in a CI/CD workflow between your local machine copy and the Platform.sh hosted copy.  (CI/CD stands for continuous integration & continuous deployment which allows you to make improvements as you gain experience and want to improve your site).


For now, what you want to do is connect the copies of your site on Platform.sh and GitHub with a copy on your local machine.  To do that use either of these two optional approaches:

a) # Go through interactive prompts to get your site from platform.sh by typing this on your command line:

       `lando init --source platformsh`

b) # OR do it non-interactively
    # NOTE: You will want to make sure you set $PLATFORMSH_CLI_TOKEN
    # and $PLATFORMSH_SITE_NAME to values that make sense for you

`lando init\
  --source platformsh\
  --platformsh-auth "$PLATFORMSH_CLI_TOKEN"\
  --platformsh-site "$PLATFORMSH_SITE_NAME"`


Details if you need them:
* If you haven't Installed Lando: [Instructions](https://docs.lando.dev/basics/installation.html#system-requirements){:target="_blank"}
* If you haven't already gotten your [Platformsh_CLI_TOKEN](https://docs.platform.sh/development/cli/api-tokens.html#get-a-token){:target="_blank"}
* If you aren't sure of the correct site name, go to the Platform.sh CLI and run `platform environment:info` which will show you all the projects you have established on this host with their name and id.
* Find more about this [Lando step](https://docs.lando.dev/platformsh/getting-started.html#quick-start){:target="_blank"}

## The practical steps by example -

Remember this basic page on Platform.sh?  We want to go back there.




Shouldn't be real hard to remember which project since we only have the one and only the 'Main' branch environment for it. 





But what we do need to make sure we do is over in the upper right corner there is a little pulldown carrot with 'My Profile' as an option under it that we want to go into:





Once you are in there, the My Profile is just the left most option on a new sub-menu bar.  And you want to scroll on over to the 'API Tokens' option where you will find a Token you want to Copy (click that blue Copy button).





Now run that 'lando init' from the terminal within VSCode (making sure you are in that local sub-directory for your project):





You should be able to answer the questions:
        - You are getting your codebase from = platformsh
        - You 'Paste' that token in we just copied
        -  Your project is the name of the project we just created.
        
        Once your local copy of the project is full installed by the prior actions, you should be able to type 'lando start' at the terminal command line, hit enter, and a local copy of your Drupal site will install.  It will be just like you saw with the host copy on Platform.sh:        





