
# Development Tools 

## Drush

You would have installed this if you followed the building of or cloning of the CI/CD Project.  

Consider Drush foundational.  It is a convenient way to execute many important commands much more quickly than winding through the GUI menu of Drupal Administration.  One of the most fundamental of all is to 'secure what you have done' by making an exported copy of your site configuration.  There is a GUI (graphical user interface) under the Administration/configuration called 'configuration synchronization' that can do this too but sometimes the GUI is more confusing and certainly a lot slower than just [exporting a configuration](../cicd/configatroot.md#site-configuration-export-AND-import) ...

		`lando drush config-export`    OR      `lando drush cex`

<font color=yellow>NOTE: If we want to 'bailout' because we messed up what were were changing we can always just import back in the prior existing configuration with `lando drush cim`.</font><br>

If drush isn't already installed and enabled do this:

`composer require --dev drush/drush`<br>

Confirm the install with this:

`./vendor/bin/drush --version`<br>
- [Drush is so basic you really need it for all the rest of the module install/enable steps](https://drupalize.me/tutorial/install-drush-using-composer?p=3516)
- [How to use Drush for your Drupal site](https://www.a2hosting.com/kb/installable-applications/optimization-and-configuration/drupal2/using-drush-for-drupal/#Enabling-modules)
- [Drupal Command List](https://drushcommands.com/)

<font color=yellow>* Take Drupal out of Maintenance Mode via Drush.</font>  `drush sset system.maintenance_mode FALSE`


## Environment Indicator module
[To easily see which environment split you are in](../cicd/envindicator.html)

`composer require drupal/environment_indicator`<br>
`drush en environment_indicator`

<br>

## Stage File Proxy module
[Real content sharing from Production to Development Environments](../cicd/stagefileproxy.md)

`composer require drupal/stage_file_proxy`<br>
`drush en stage_file_proxy`

<br>

## PathAuto
As you build out each page of your site you are presented with an option where you can provide a specific URL for that page.

<img src="../modules/images/pathauto1.png"  width="550">

If you use that, you might take something which may default to this...

<img src="../modules/images/pathauto3.png"  width="250">

And make it look like this.  A more human readable, meaningful URL.

<img src="../modules/images/pathauto2.png"  width="350">

See how the [Pathauto module](https://www.webwash.net/automatically-generate-url-aliases-using-pathauto-drupal-8/) is simply a way that you can make this process more automatic; or hear more about it in an [ Overview of how path names work with Drupal node entities.](https://www.youtube.com/watch?v=9SvNuhk4ZUA&t=28s)  If you are building a tiny site then you really aren't leveraging the value of a content managment system like Drupal.  But if you are having frequently updated content, potentially from various sources, even fed to you via RSS, then having more automatic URL naming is important.

You may find that Pathauto doesn't run deep enough to suit your needs.  You can extend its reach with the [Sub-Pathauto module.](https://www.drupal.org/project/subpathauto)  If you happen to have a site that is serving different departments in a large organization, company or government you will find this addition helpful.  And it also plays a nice [role in combination with Views, Media, etc. as explained here.](https://lostcarpark.com/advent/2023/2/subpathauto-and-friends)

<br>

Having it on during development might get you to think about 'naming' with end-user thinking in sight.  Instead of a path that is something like a node and its number you might have a content category and a node title; and you can use 'Tokens' in the naming strategy for the paths. [See adding the Token module.](../modules/development.md#token-module)<br>

`composer require drupal/pathauto`<br>
`drush en pathauto`

<br>

## Token module
It is easiest to think about tokens as variables.  One part of your site might contain a variable like the name of the logged in user and you want to use that variable in another section of the site.  The Token module provides visiblity into the availble variables and the syntax for how you need to refer to them.<br>

<img src="../modules/images/token1.png"  width="450">

[This summary](https://gole.ms/blog/tokens-drupal-how-they-work-and-what-they-can-give-your-website) tells more about the basic categories of tokens and how the module helps you use them.  The prior module, PathAuto, is a common one that taps into your site's tokens to spruce up the URLs people see going from page to page.  An overview of [how those two modules work together](https://www.volacci.com/drupal-seo-guide/drupal-token-system) also helps see more clearly how you might use them in other contexts.  [Token's also work with taxonomy in valuable ways](https://www.youtube.com/watch?v=5A3y0N_1Ufk).<br>

Install and enable the token module as usual...<br>

`composer require drupal/token`<br>
`drush en token`

<br>

## Token Filter module
You are likely to want to use tokens in field replacement values.  This will get you loads more value from Tokens.  To do that you also want to install the [Token Filter module.](https://www.drupal.org/project/token_filter)  You can see [how to use this module in this quick training overview.](https://ostraining.com/blog/drupal/tokens-in-drupal-fields/)  You might use this, for example, by creating a block you place in the footer with your site name and a copywrite notice with date.  You could use your CKEditor to insert the token values for site name and for date in a custom year only format in the block you then place in the footer region of your site.<br>

`composer require drupal/token_filter`<br>
`drush en token_filter`

<br>

## Masquerade module
This module lets you switch users and back to your own account.  You can experience testing what it is like for various log-in roles. Does it work for an anonomous user, for a logged in non-paid users, for a subscribing user, for a contributing editor, etc.<br>

`composer require drupal/masquerade`<br>
`drush en masquerade`

<br>

## Responsive Preview module
Masquerade gets you the feel of different user type experiences. Responsive Preview gets you the feel of different device experiences. This module provides a way to quickly test the look of your site in various responsive view breakpoints while you are doing development.  They warn it isn't a perfect simulation but pretty solid.<br>

`composer require drupal/responsive_preview`<br>
`drush en responsive_preview`

<br>

## Devel module
As valuable as masquerading as different users or like you are on different devices may be, having mock content can be very helpful to really get a feel for how a finished site will work.  The Devel modules isgood to generate fake content to better see what things will look like without having to spend a ton of time manually loading real content.  But before you go down that road, if you are using our [CI/CD Process](../book/drupalcicd.md) you may want to consider the fact we are using the [Stage File Proxy Module](../cicd/stagefileproxy.html) to share production ('main') level data with our 'local' lando site in a tight contextual manner that may provide even better full perspective developer experience.<br>

`composer require 'drupal/devel`<br>
`drush en devel`

<br>

## Devel Generate Alternative

### Add Another module
You can put this in early if you are dropping in some content while developing so you get a feel for your site but don't like Devel's Generate output as realistic enough.  Or, you can put it in after your site is built and you are loading in a bunch of content one after the next.  What it does is put in an 'Add Another' button to quickly create additions nodes after creating a new node. You can customize the text on that tab with the [Custom Add Another](https://www.drupal.org/project/custom_add_another) module.<br>

`composer require drupal/addanother`<br>
`drush en addanother`

<br>

## WebProfiler module
WebProfiler adds a toolbar at the bottom of every page and shows you all sorts of stats such as the amount of database queries loaded on the page, which services are used and much more. This was previously part of the Devel module but is now separate.<br>

`composer require drupal/webprofiler`<br>
`drush en webprofiler`

<br>

## Devel Kint Extras module
This module was parsed out of the prior Devel module into a separate tool.  Makes sense because this tool starts to move you past a site builder level to true developer skill set. The [Kint Debugging Tool](https://kint-php.github.io/kint/) might be of interest only to some of the more advanced users.<br>

`composer require drupal/devel_kint_extras`<br>
`drush en webprofiler`

<br>

## Admin Toolbar module
This is an alternative layout to the out-of-the-box toolbar that developers and site builders normally work with.  It used more of the vertical space of a pulldown style tool bar rather than drilling page by page into submenus; thus faster for developers.<br>

`composer require 'drupal/admin_toolbar`<br>
`drush en admin_toolbar`

<br>

## Admin Dialogs module
Sometimes repetative actions working with various site building or content additions requires a sequence of page loads.  The page loads are a little slower than just popping up a modal for something like a 'delete' action confirmation.  This [module can](https://www.drupal.org/project/admin_dialogs) be configured to achieve that and behaves with the Admin Toolbar module if you want to add both.

`composer require 'drupal/admin_dialogs`<br>
`drush en admin_dialogs`

<br>

##  Autosave Form module

Is a 'maybe' addition to development and content editing.  It does NOT retain pure true revision versions but has its own temporary storage logic while you are working.  It is set at 60 second for an autosave but should be configurable.

`composer require 'drupal/autosave_form`<br>
`drush en autosave_form`

<br>


## Feeds module

Can be used to [grab CSV and other file format data plus HTML from another site, and import it.](https://www.youtube.com/watch?v=VcooCT50PFY)  It is another candidate for pulling in Taxonomies or even things like an airport data sets to preload nodes for all the airports.  Don't forget the 'Feeds Tamper' module that works with it to add more functionality like string replacements or other file manipulation functions for cleanup actions during import.  Those can be increasingly important if you are creating a dyanamic feed update with the time based function that is retrieving information from say a remote URL or other source system.<br>

Review module status [here to make sure it meets your stablity requirement settings.](https://www.drupal.org/project/feeds)

<br>

## Development Mode module

This module is to stop cache, aggregation, turn on debug, in your 'Development' Split.  If you use the [Drupal CI/CD Project workflow template](..cicd/cicdoverview.md) 
 provided elsewhere on this site, you do NOT need to add this module because the functions it provides have already been incorporated via other means. <br>
 
`composer require –dev drupal/dev_mode`<br>
`drush en dev_mode`

<br>

## Backup and Migrate module

Using the [Drupal CI/CD Project workflow template,](..cicd/cicdoverview.md) provided elsewhere on this site, you do NOT need to add this module because you are going to set up your backup in the Platform.sh host and your Git Repository version control system.  However, it might come in to play for migration of a site later in your development or site building work.<br>

`composer require drupal/backup_migrate`<br>
`drush en backup_migrate`

<br>

## Content Model & Site Documentation
The [Content Model & Site Documentation module](https://www.drupal.org/project/content_model_documentation) is something too often ignored.  But there is a way you can install this module in Drupal as you get started and it puts the tools you need to document right at the place you are working.  That might be just an extra tab on a content type you are setting up or it might be a trigger point where content managers can go to see guidelines on how they should present content.  This [video overview, starting aroun 16.5 minutes in, gives you the details.](https://www.youtube.com/watch?v=TYXz7D14mMA)



## Password Reset Landing Page module

Because users forget to change their password after using a one time login link in their password reset email this module enhances the original password reset landing page by letting a user set their new password at the same time they "log in" using the one-time-login link.<br>

`composer require drupal/prlp`<br>
`drush en prlp`

<br>

## Super Login module

Take control of the appearance of the log in.<br>

So people might login via Email or username, email only or username only.  You can also adjust the layout and theming of the forms to be more user friendly and visually pleasing. The module's theme can be turned off and customized in your own stylesheets.  Show a caps lock warning message and control other presentation things.<br>

`composer require drupal/super_login`<br>
`drush en super_login`

<br>

## Login w/Google modules

This is a group of modules that takes a little set up but allows users to login with their Google account.  The [Login with Google module set up steps](https://www.codimth.com/blog/web/drupal/how-login-google-drupal-8-9)  provides the details on how to do this.<br>

<br>

## Redirect module

Assures external links back to your site pages work if you change your site but want to assure its connections by others to your prior site are retained and credited.<br>

`composer require drupal/redirect`<br>
`drush en redirect`

<br>

## Ctools or Chaos Tools module

If you just installed PathAuto, it already installed Ctools.<br>

`composer require drupal/ctools`<br>
`drush en ctools`


<br>
<br>
<br>

[Learn More - Drupal Modules List](../chapters.md#drupal-modules)

