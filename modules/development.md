
# Development Tools Modules

## Drush
You would have installed this if you followed the building of or cloning of the CI/CD Project.  

Consider Drush foundational.  It is a convenient way to execute many important commands much more quickly than winding through the GUI menu of Drupal Administration.  One of the most fundamental of all is to 'secure what you have done' by making an exported copy of your site configuration.  There is a GUI (graphical user interface) under the Administration/configuration called 'configuration synchronization' that can do this too but sometimes the GUI is more confusing and certainly a lot slower than just [exporting a configuration](../cicd/configatroot.md#site-configuration-export-AND-import) ...

		`lando drush config-export`    OR      `lando drush cex`

<font color=yellow>NOTE: If we want to 'bailout' because we messed up what were were changing we can always just import back in the prior existing configuration with `lando drush cim`.</font>

If drush isn't already installed and enabled do this:

`composer require --dev drush/drush`<br>

Confirm the install with this:

`./vendor/bin/drush --version`

[Drush is so basic you really need it for all the rest of the module install/enable steps](https://drupalize.me/tutorial/install-drush-using-composer?p=3516)


## Environment Indicator module
[To easily see which environment split you are in](../cicd/envindicator.html)

`composer require drupal/environment_indicator`<br>

`drush en environment_indicator`

## Stage File Proxy module
[Real content sharing from Production to Development Environments](../cicd/stagefileproxy.md)

`composer require drupal/stage_file_proxy`<br>

`drush en stage_file_proxy`


## PathAuto
As you build out each page of your site you are presented with an option where you can provide a specific URL for that page.

<img src="../modules/images/pathauto1.png"  width="550">

If you use that, you might take something which may default to this...

<img src="../modules/images/pathauto3.png"  width="250">

And make it look like this.  A more human readable, meaningful URL.

<img src="../modules/images/pathauto2.png"  width="350">

Pathauto is simply a way that you can make this process more automatic; [Podcast Overview](https://www.youtube.com/watch?v=3l8ihak4_uk). If you are building a tiny site then you really aren't leveraging the value of a content managment system like Drupal.  But if you are having frequently updated content, potentially from various sources, even fed to you via RSS, then having more automatic URL naming is important. 

Having it on during development might get you to think about 'naming' with end-user thinking in sight.  Instead of a path that is something like a node and its number you might have a content category and a node title; and you can use 'Tokens' in the naming strategy for the paths. [See adding the Token module]() 

`composer require drupal/pathauto`<br>
`drush en pathauto`

## Token module
It is easiest to think about tokens as variables.  One part of your site might contain a variable like the name of the logged in user and you want to use that variable in another section of the site.  The Token module provide visiblity into the availble variables and the syntax for how you need to refer to them.  

<img src="../modules/images/token1.png"  width="450">

[This summary](https://gole.ms/blog/tokens-drupal-how-they-work-and-what-they-can-give-your-website) tells more about the basic categories of tokens and how the module helps you use them.  The prior module, PathAuto, is a common one that taps into your site's tokens to spruce up the URLs people see going from page to page.  An overview of [how those two modules work together](https://www.volacci.com/drupal-seo-guide/drupal-token-system) also helps see more clearly how you might use them in other contexts. 

Install and enable the token module as usual...

`composer require drupal/token`<br>
`drush en token`






Devel (good to generate fake content, among other things, to better see what things will look like without having to spend a ton of time manually loading real content.) 
composer require 'drupal/devel:^4.1'
drush en devel


Admin Toolbar (an alternative layout to the out-of-the-box toolbar that developers and site builders normally work with.  It used more of the vertical space of a pulldown style tool bar rather than drilling page by page into submenus; thus faster for developers).

composer require 'drupal/admin_toolbar:^3.0'





The Masquerade Module lets you switch users and back to your own account so you can do your experience testing of what it is like for various log in role statuses to experience your site.
composer require 'drupal/masquerade:^2.0@beta'


The Responsive Preview Module is a way to quickly test the look of your site in various responsive view breakpoints while you are doing development.  They warn it isn't a perfect simulation but pretty solid.
composer require 'drupal/responsive_preview:^1.0'

The Autosave Form Module is a 'maybe' addition to development and content editing.  It does NOT retain pure true revision versions but has its own temporary storage logic while you are working.  It is set at 60 second for an autosave but should be configurable.
composer require 'drupal/autosave_form:^1.2'



Backup Add section on backup plan in coordination with hosting provider's set up, Git repo strategy, and local Dev rebuild strategy.

Feeds Module is one that can be used to grab CSV and other file format data plus HTML from another site, and import it.  It is another candidate for pulling in Taxonomies or even airport data sets to preload nodes for all the airports.  It is in an Alpha 10 for Drupal 9 and it lists as not secure; however, if you install it to build and then remove it afterward it should be fine.




Development Mode module (stop cache, aggregation, turn on debug, in your 'Development' Split:
composer require –dev drupal/dev_mode
drush en dev_mode

Devel module (generate mock content, masquerade user, redirect email, etc.):
composer require drupal/devel
drush en devel



Backup and Migrate module:
composer require drupal/backup_migrate
drush en backup_migrate

Password Reset Landing Page module (clarifies password reset process from core):
composer require drupal/prlp
drush en prlp

Super Login module (take control of the appearance of log in):
composer require drupal/super_login
drush en super_login




Redirect module (assures external links back to your site pages work if you change your site):
composer require drupal/redirect
drush en redirect

Ctools or Chaos Tools module (If you just installed PathAuto, it already installed Ctools.):
composer require drupal/ctools
drush en ctools





