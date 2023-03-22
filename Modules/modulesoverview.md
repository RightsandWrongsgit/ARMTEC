
# Drupal Modules

[Core Drupal](https://www.drupal.org/project/drupal) has much of what you need.  Combined with the [CI/CD Workflow](../book/drupalcicd) Process that gets your development project base in place, you are off to the races in building a website.

#### Your Plan Guides Your Modules
Of course, you hopefully have penciled up or formally designed the site you are building. Some [tools](../book/opensource.html] can move you well down that process.  Worst case senario, you can just use a drawing program, a presentation tool like PowerPoint or FrontPage, or a cocktail napkin.

#### Core and Contributed Modules
Core Drupal has a ton of what are known as modules included right in it.  Some are active or enbabled automatically at install.  Others are there but you need to enable them.  These basic items give you the bricks and mortar, studs and wall board, kind of stuff to build something.  However, you will also find that many have plowed the ground before you and built all sorts of stuff that they kindly make available to you for free.  You have got to love [Open Source](book/opensource.md).  These are known as "contributed modules".  And they aren't just random junk.  I mean they go through a pretty serious curation process.  That said, many would benefit from your contribution to the community by being a 'documentation writer'.  Also, there are like 40-50 thousand of these contributed modules.  That means that a whole bunch are pretty low level utility-like things.   It also means that finding what you want takes some searching and testing that they do what you really want.

## Additions to CI/CD Workflow Base
To make life somewhat easier, ARMTEC has its own list of favorites that can guide toward some contributed modules that are pretty commonly important to add to your base site.  Why aren't these just part of Drupal Core to begin with?  Same reason they aren't part of our CI/CD Workflow base install (some key to that process are in fact installed and enabled for that).  But some web builds simple don't need the overhead of extra modules that they won't use.  So a minimalistic approach is taken with the expectation that the user will install & enable what they want to accomplish their goals.

The [CI/CD Workflow](../book/drupalcicd) puts in place modules to provide a split of configurations for 'main' (production site), 'staged', 'develop', and 'local' (Lando) environments.  It also includes an 'environment indicator' to make it super clear where you are working.  Outlined in that set up is a [table that suggests what modules and configuration settings you might what in each environment](../cicd/configsplit3.html).  Some modules you want in all environments and some you want in only one environment.  Those you want in all, are easiest to add before you start activating your splits; in our case, in the starting point only situation where 'local' is connecting directly with 'main'.  Here are categories of modules that we find valuable.  Obviously [many, many more are available(https://www.drupal.org/project/project_module)

- [Development]()
- [Taxonomy]()
- [Special Field Convenience]()
- [Content Editing]()
- [Media]()
- [Mapping]()
- [Search]()
- [Themes]()
- [Menu Enhancements]()
- [Forms]()
- [Roles/Content Moderation]()
- [Mail]()
- [Marketing]()
- [Tracking]()
- [Security]()
- [Legal/Regulatory/Compliance]()




