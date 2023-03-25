
Set up your Development Tools:

Here is a good list of what you probably want to include right out of the box beyond the core items that are a standard part of Drupal 9.


composer require drush/drush


Once Drush is installed, it becomes a convenient way to execute many important commands.  One of the most fundamental of all is to 'secure what you have done' by making an exported copy of your site configuration.  There is a GUI (graphical user interface) under the Administration/configuration called 'configuration synchronization' that can do this too but sometimes the GUI is more confusing and certainly a lot slower than just doing these next few statements from the command line after you have spent time installing and enabling all the other recommended modules. So you might run this to secure that effort and practice the skill as you to the additions:

So you will be doing things in your Drupal application in whatever configuration is ACTIVE and you want to save those changes by EXPORTING them to make them available to the others ….

remember we want to KEEP what is in ACTIVE so we EXPORT it …

		lando drush config-export    OR      lando drush cex

NOTE: If we want to 'bailout' because we messed up what were were changing we can always just import back in the prior existing configuration with ‘lando drush cim’


_________________________________________________________________________

Many developers like to use things beyond Drush to help their efforts.  Here are some 'optional' modules to consider:

Devel (good to generate fake content, among other things, to better see what things will look like without having to spend a ton of time manually loading real content.) 
composer require 'drupal/devel:^4.1'
drush en devel


Admin Toolbar (an alternative layout to the out-of-the-box toolbar that developers and site builders normally work with.  It used more of the vertical space of a pulldown style tool bar rather than drilling page by page into submenus; thus faster for developers).

composer require 'drupal/admin_toolbar:^3.0'



PathAuto (This is also a module that you may want to wait to turn on because it is more about the 'appearance' of how paths look; to give them alias names that are much more meaningful to the user of your site.  However, having it on during development might get you to think about 'naming' with end-user thinking in sight.  Instead of a path that is something like a node and its number you might have a content category and a node title; and you can use 'Tokens' in the naming strategy for the paths (See adding the Token module under the 'fields' section.)

composer require 'drupal/pathauto:^1.8'

The Masquerade Module lets you switch users and back to your own account so you can do your experience testing of what it is like for various log in role statuses to experience your site.
composer require 'drupal/masquerade:^2.0@beta'


The Responsive Preview Module is a way to quickly test the look of your site in various responsive view breakpoints while you are doing development.  They warn it isn't a perfect simulation but pretty solid.
composer require 'drupal/responsive_preview:^1.0'

The Autosave Form Module is a 'maybe' addition to development and content editing.  It does NOT retain pure true revision versions but has its own temporary storage logic while you are working.  It is set at 60 second for an autosave but should be configurable.
composer require 'drupal/autosave_form:^1.2'



Backup Add section on backup plan in coordination with hosting provider's set up, Git repo strategy, and local Dev rebuild strategy.

Feeds Module is one that can be used to grab CSV and other file format data plus HTML from another site, and import it.  It is another candidate for pulling in Taxonomies or even airport data sets to preload nodes for all the airports.  It is in an Alpha 10 for Drupal 9 and it lists as not secure; however, if you install it to build and then remove it afterward it should be fine.


Environment Indicator module (To easily see which environment split you are in):
composer require drupal/environment_indicator
drush en environment_indicator

Development Mode module (stop cache, aggregation, turn on debug, in your 'Development' Split:
composer require –dev drupal/dev_mode
drush en dev_mode

Devel module (generate mock content, masquerade user, redirect email, etc.):
composer require drupal/devel
drush en devel

Stage File Proxy module (Real content sharing from Production to Development Environments):
composer require drupal/stage_file_proxy
drush en stage_file_proxy

Backup and Migrate module:
composer require drupal/backup_migrate
drush en backup_migrate

Password Reset Landing Page module (clarifies password reset process from core):
composer require drupal/prlp
drush en prlp

Super Login module (take control of the appearance of log in):
composer require drupal/super_login
drush en super_login

Token module:
composer require drupal/token
drush en token

PathAuto module:
composer require drupal/pathauto
drush en pathauto

Redirect module (assures external links back to your site pages work if you change your site):
composer require drupal/redirect
drush en redirect

Ctools or Chaos Tools module (If you just installed PathAuto, it already installed Ctools.):
composer require drupal/ctools
drush en ctools





