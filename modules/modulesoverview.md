
# Drupal Modules

[Core Drupal](https://www.drupal.org/project/drupal) has much of what you need.  Combined with the [CI/CD Workflow](../book/drupalcicd) Process that gets your development project base in place, you are off to the races in building a website.

#### Your Plan Guides Your Modules
Of course, you hopefully have penciled up or formally designed the site you are building. Some [tools](../book/opensource.html] can move you well down that process.  Worst case senario, you can just use a drawing program, a presentation tool like PowerPoint or FrontPage, or a cocktail napkin.

#### Core and Contributed Modules
Core Drupal has a ton of what are known as modules included right in it.  Some are active or enbabled automatically at install.  Others are there but you need to enable them.  These basic items give you the bricks and mortar, studs and wall board, kind of stuff to build something.  However, you will also find that many have plowed the ground before you and built all sorts of stuff that they kindly make available to you for free.  You have got to love [Open Source](book/opensource.md).  These are known as "contributed modules".  And they aren't just random junk.  I mean they go through a pretty serious curation process.  That said, many would benefit from your contribution to the community by being a 'documentation writer'.  Also, there are like 40-50 thousand of these contributed modules.  That means that a whole bunch are pretty low level utility-like things.   It also means that finding what you want takes some searching and testing that they do what you really want.

## Additions to CI/CD Workflow Base
To make life somewhat easier, ARMTEC has its own list of favorites that can guide toward some contributed modules that are pretty commonly important to add to your base site.  Why aren't these just part of Drupal Core to begin with?  Same reason they aren't part of our CI/CD Workflow base install (some key to that process are in fact installed and enabled for that).  But some web builds simple don't need the overhead of extra modules that they won't use.  So a minimalistic approach is taken with the expectation that the user will install & enable what they want to accomplish their goals.

The [CI/CD Workflow](../book/drupalcicd) puts in place modules to provide a split of configurations for 'main' (production site), 'staged', 'develop', and 'local' (Lando) environments.  It also includes an 'environment indicator' to make it super clear where you are working.  Outlined in that set up is a [table that suggests what modules and configuration settings you might what in each environment](../cicd/configsplit3.html).  Some modules you want in all environments and some you want in only one environment.  Those you want in all, are easiest to add before you start activating your splits; in our case, in the starting point only situation where 'local' is connecting directly with 'main'.  Here are categories of modules that we find valuable.  Obviously [many, many more are available](https://www.drupal.org/project/project_module)

### Before Adding Others
Drupal core is great and has a number of super modules; some of which need to be 'turned on' or enabled.

Modules already in core, but should be enabled: (note that our basic lando/platform.sh install approach automatically included the Drush module and enabled it; this is key because we are going to short cut enabling other modules using Drush)

From within Core, enable these -

`drush en responsive_image`<br>
`drush en media`<br>
`drush en media_library`<br>
`drush en link`

You are going to benefit from a bunch more modules that others had contributed to Drupal as an [open source](../book/opensource.md) CMS.  So the very first "extra" module you are going to put in place is one that simply better categorizes modules in the 'Administration/Extend' part of Drupal so it is easier to track what is in, what is enabled, and thus, what else you might want to add.  This is the 'Module Filter module': 

`composer require drupal/module_filter`<br>
`drush en module_filter`

## Categories of Modules

- [Development]()
- [Taxonomy]()
- [Special Field Convenience]()
- [Content Editing]()
- [Trimming Text Summaries](../modules/smarttexttrim.md)
- [Media]()
- [Mapping]()
- [Flagging](../modules/flagging.md)
- [Search]()
- [Themes]()
- [Menu Enhancements]()
- [Forms](../modules/forms.md)
- [File Viewer](../modules/filedisplay.md)
- [Roles/Content Moderation]()
- [Mail]()
- [Marketing]()
- [Tracking]()
- [Security]()
- [Legal/Regulatory/Compliance]()




## Module Filter module for better categorization of what you install/enable:
composer require drupal/module_filter
drush en module_filter

From within Core, enable these -
drush en responsive_image
drush en media
drush en media_library
drush en link

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

[Linking two related entities (e.g. person like spouses, children)](https://www.drupal.org/project/cer)

## MODULES IMPROVING BASIC SITE FUNCTIONS 
(These are common in many sites.  CKEditor & Taxonomy Improvements listed separately.)


Linked Field module: 
composer require 'drupal/linked_field
drush en linked_field

Linkit module: 
composer require 'drupal/linkit
drush en linkit

Iframe module:
composer require drupal/iframe
drush en iframe

Modal module:
composer require drupal/modal_page
drush en modal_page

Exclude Node Title module:
composer require drupal/exclude_node_title
drush en exclude_node title

Smart Trim module:
composer require drupal/smart_trim
drush en smart_trim

Media Entity Embed module (Inline Entity Form, Entity Browser, Entity Embed dependencies):
"consider this module a priority" 
composer require drupal/media_entity_browser
drush en media_entity_browser

Entity Reference Revisions module:
composer require drupal/entity_reference_revisions
drush en entity_reference_revisions

Entity Browser Enhanced module:
composer require drupal/entity_browser_enhanced
drush en entity_browser_enhanced

Entity Usage module:
composer require drupal/entity_usage
drush en entity_usage

Entity Reference Preview module:
composer require drupal/entity_reference_preview
drush en entity_reference_preview
Block Visibility Groups module (enhancement to control and placement of blocks over core):
"greater than sliced bread" category! 
composer require drupal/block_visibility_groups
drush en block_visibility_groups

Views Block Expose Filter Blocks module:
composer require drupal/views_block_filter_block
drush en views_block_filter_block

Views Flipped Table module:
composer require drupal/views_flipped_table
drush en views_flipped_table

Views Infinite Scroll module:
composer require drupal/views_infinite_scroll
drush en views_infinite_scroll

Add Another module (sort of speed copy another iteration of a node as a good near replication):
composer require drupal/addanother
drush en addanother

## Content Type Modules

[Acquia](https://www.acquia.com/) is a commercial company founded by the [original developer of Drupal.](https://dri.es/)  They continue to [Open Source](../book/opensource.md) many of the tools they use.  You might want to glance through their GitHub repository, especially their [Acquia/CMS that provides some modules aimed at building some valuable content types.](https://github.com/acquia/acquia_cms/tree/develop/modules) for things like Person, Event, Place, Document, etc.


<br>
<br>
<br>

[Learn More - Drupal Modules List](../chapters.md#drupal-modules)



