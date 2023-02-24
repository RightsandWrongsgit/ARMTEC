
# Mid-Point Update

## Where are we and What's Next?

- At this point, we have Platform.sh running our 'main' site as host, we have a copy of that locally running on Lando, and the two are linked to each other as well as GitHub.<br>

- We are working with our local Lando based site through a VSCode interface that allows us …<br>
-- To see the sub-directories and file list on the left<br>
-- To see a 'Terminal' on the lower right to run 'Command Line' stuff<br>
-- To see the actual content and syntax in any file we click on from the left panel to show up in a view pane on the upper right.  And we can edit files right there when we want.<br>
-- In the bottom left menu bar we see an indicator that tells us we are on the Git 'main' branch locally as well. <img src="../cicd/captures/midpoint1.png"  width="50"><br> 
-- We remember that we can hit 'Shift', 'Command', 'P' to open the Command Palette to do stuff <img src="../cicd/captures/midpoint2.png"  width="150"><br> 

- We are headed toward setting up additional 'environments' so we have <font color=red>'main', 'staged','develop', and 'local'</font> branches.  We will use standard [Git branching](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell) to create the additional environments.  First we will branch 'staged' off of 'main'.  Then we will branch 'develop' off 'staged'.  This sequence allows us to [Git merge](https://git-scm.com/docs/git-merge) back up that chain. 
 - 'local' is simply the physical environment on our own machine; we will we working in a Lando container here.  We can actually use this local Lando physical environment against any of the other code environments on our Platform.sh host <font color=red>WE WON'T because that defeats the value of our CI/CD workflow</font>.<br> 
 - 'develop' is the code environment on our host that we will speak to most directly from our Lando 'local' environment.  Expect to see the name 'develop' in the lower left corner of your VSCode IDE when you are later working on enhancements to your website.<br> 
 -'staged' is the host environment where we will be testing those changes and enhancements before deploying them to 'main'.  Testing might be technical stuff, it might be just driving around in a copy of your site to see how things look and work after you did the changes just to be sure you like them, or it might be sending a link to that staged environment so a client or a friend can see if they like it before you deploy it.<br> 

- While these environments are pretty close mirrors of one another, it doesn't make sense to have all of the same stuff operating in each.  For example, your 'main' site may have something like Google Analytics running in it but you want that turned off in your 'develop' copy so you don't screw up counts, statistics, etc.  Or, you might have some tools installed in the 'develop' copy of the site that make it easier to do some stuff as you work on it but you don't want those tools out in 'main' so your site users stumble into them.  Shortly, the steps to uniquely set up these key highly coordinated differences will be provided.<br>

- What we want to do in preparation <font color=red>BEFORE</font> we set up these additional environments is to …<br>
-- Install and enable some of the modules we might anticipate using on our site (don't worry, we can add others later, it is just easier up front because then they will automatically be present across all three).<br>
-- Automatically, that is, unless we <u>Don't Want<u> them to be.  What we will be learning about is how Drupal has something called [Configuration](https://mikemadison.net/blog/2020/6/26/drupal-configuration-introduction) and this tells how an environment is set up.  So that we can achieve having differences between our environments, we will be installing a Config_Split module.  Think about Config_Split as basically '**turning off**' stuff we don't want operating in a specific environment; so, think that we really have all stuff present everywhere but just not always active in each environment.<br> 

  
  [- Next -]()
