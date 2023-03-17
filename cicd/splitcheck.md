
# Config_Split Module in place
## Let's set it in motion -

With config_split installed and enabled plus sub-directories set up for our splits, we need to point the module to those locations.  We go into the 'Configuration' menu in Administration and find the 'Development' section.  There you will be able to select the 'Configuration Split settings' option.  

<img src="../cicd/captures/splitcheck1.png"  width="400">

There we will need to 'Add Configuration Split setting' for each of the named splits we establish.

<img src="../cicd/captures/splitcheck2.png"  width="300">

Let's start with just the basics of naming and pointing to the location sub-directory for the splits we set up.  There are fill-in boxes for the name (Label), an optional description, the location (Folder), and a checkbox for 'Active' or not.  We are leaving the Weight option at its default zero.  We are 'unchecking' the 'Active' box.  In the example below, we are setting up main and pointing to the pointing to the folder location sub-directory we established for that environment which is   ../config/main

<img src="../cicd/captures/splitcheck3.png"  width="800">

Scroll past the 'Complete split' and 'Conditional split' sections; each of which offer options at the module or  configuration item level.  Don't mess with these for now.  However, it is informative to see a list of your modules checkboxes and configuration items with checkboxes; and to glance at the names of the configuration items looking a lot like the file names you 'drush cex' exported as yml file but without that final file name extension showing.  
Just scroll on past the two checkboxes but this time leave them checked.  Then hit the "Save" button 

<img src="../cicd/captures/splitcheck4.png"  width="400">

When you have all four environments named and pointing to their sub-directory homes, you should see something like this:

<img src="../cicd/captures/splitcheck5.png"  width="600">

* John Picozzi "Configuration Management & Config Split" is a nice but long video on some additional options for splits like even Multi-site environments.  He doesn't use the same approach to environment case detection and the 'case' test; but something fairly similar.  He also doesn't do the environment-indicator but actually uses system.site within split configurations to do the same sort of thing manually as a demonstration of the yml level conditional (rather than full module) splits. 
https://www.youtube.com/watch?v=rwKjVVhOHs4
