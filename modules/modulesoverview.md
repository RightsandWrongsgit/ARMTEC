
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

## Module Filter
#### A module for better categorization of what you install/enable

You are going to benefit from a bunch more modules that others had contributed to Drupal as an [open source](../book/opensource.md) CMS.  So the very first "extra" module you are going to put in place is one that simply better categorizes modules in the 'Administration/Extend' part of Drupal so it is easier to track what is in, what is enabled, and thus, what else you might want to add.  This is the 'Module Filter module': 

`composer require drupal/module_filter`<br>
`drush en module_filter`

# Categories of Modules

When you think about adding modules to your Drupal website on top of the [CI/CD Project Base](../book/drupalcicd.md) consider two schools of thought.  One of these is obviously what sort of extra features or functions you want to include on the site.  The other consideration is around the stage you are in the project. For example, you want tools while you are building your site that are 'Development' related modules; and you may keep these in the 'local' and 'develop' environments simply because you are in a continous improvement mindset.  But do you really want to have Google Analytics running during initial development?  There are lots of other modules that you will want in an 'Active' website that you won't install until you are ready to launch.  Consider both factors as you plan your website.


  - [Development Modules](/modules/development.md)
  - [Fields Modules](/modules/fields.md)
  - [Trim Text & Present Lists Better](/modules/smarttexttrim.md)
  - [Flagging Modules](/modules/flagging.md)
  - [Taxonomy](/modules/taxonomy.md)
  - [Faceted Search](/modules/facetedsearch.md)
  - [Entity Edits/Links/Reference](/modules/entityref.md)
  - [Content Type Entity](/modules/contenttype.md)
  - [Views](/modules/views.md)
    - [Create a Search Page with Views](https://www.webwash.net/search-page-using-views-in-drupal/)
    - [Create your own Administration Page with Views](https://www.webwash.net/create-admin-page-using-views-in-drupal/)
  - [Users, Roles, Permissions](/modules/roles.md)
  - [Groups](/modules/groups.md) 
  - [Forms](/modules/forms.md)
  - [Comments: Perhaps a Quick Blog](https://www.webwash.net/how-to-manage-comments-in-drupal/) 
  - [File Viewer](/modules/filedisplay.md)
  - [Events->Conditions->Actions](/modules/ECA.md)
  - [Events: Manage One](/modules/events.md)  
  - [Performance](/modules/performance.md)
  - [Security](/modules/security.md)
  - [Mapping](/modules/mapping.md)
    - [Example: Map & Taxonomy Node Build](/modules/mapinnodes.md)
  - [Links & Modals](/modules/linksmodals.md)
    - [Create your own module: Embeded YouTube Video](https://www.webwash.net/how-to-create-a-custom-field-formatter-in-drupal-8/) 
  - [Email](/modules/email.md)
  - [Media](/modules/media.md)
  - [Layout Builder](/modules/layoutbuilder.md)
  - [SEO Modules](/modules/SEO.md)
  - [Active Site Modules](/modules/activesite.md)
  - [Content Moderation](/modules/contentmoderate.md)





<br>
<br>
<br>

[Learn More - Drupal Modules List](../chapters.md#drupal-modules)



