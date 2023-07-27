# Drush

Drush is sort of the [(CLI)](https://www.techtarget.com/searchwindowsserver/definition/command-line-interface-CLI?Offer=abt_pubpro_AI-Insider) of Drupal.  It has a scripting functionality with a ton of predefined useful commands.  Do you have to use it? NO.  Will you want to use it? ABSOLUTELY!

## First Use Value

Drupal site building can be done from the graphical user interface (GUI) Administration menu.  Every time you watch some training video on something you want to do with your site, it will likely emphasize "Clear Your Cache" to make it show up.  Drupal is loaded with a bunch of [Cache's](https://www.drupal.org/docs/7/managing-site-performance-and-scalability/caching-to-improve-performance/caching-overview) which play a role in its strong performance; a good thing.  Basically this means something of temporary value is stored for quick retrieval but if something you do changes what is stored it needs to be cleared out.  Don't worry, in a running site all this stuff is automatic.  But while you are building your site you need to clear the cache while working to see if what you did 'took'.   So you find yourself going down a whole series of clicks to the right spot in the GUI interface to get to the button to do that.  Since you are likely to use an [integrated development environment](https://rightsandwrongsgit.github.io/ARMTEC/book/ide.html) where you see your project plus have a command line available right there, most people find it much quicker to simply type …

`drush cr`

To see more about both options to clear the cache [watch this video](https://www.youtube.com/watch?v=-evRieC6Y3U&t=41s)

## Installing Drush

Often times you don't have to do anything special to have Drush installed.  That is because it is so commonly used that it rides along with your basic Drupal initial installation.  The [Drupal CI/CD Base Project](https://rightsandwrongsgit.github.io/ARMTEC/book/drupalcicd) we provide already includes it.

If you find yourself needing to install Drush independently there are a few important things to consider.  First, Drush leverages the fact that you are using Drupal via a [Composer](https://rightsandwrongsgit.github.io/ARMTEC/book/Novice.html#setting-up-your-basic-system) based installation; so make sure you are doing it that way.  Second, people who get into developing with Drupal often take on more than one site and have the local development copy of the various sites on their local hard drive in different directories.  Each project needs access to Drush and normally if it came as part of just installing with a single Drupal installation it is directly associated with the project.  When you have multiple Drupal projects there are ways that you add to your Bash or ZSH Shells the pathway instructions to make Drush visible and available to multiple Drupal projects across your local machine.  The "how to" for that is best found right from the Drush website.

## Show me Drush

 [Drush website](https://www.drush.org)
