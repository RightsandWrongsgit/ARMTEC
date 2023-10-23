
# Regions & Blocks

[Regions & Blocks](https://www.webwash.net/courses/managing-blocks-in-drupal/l/overview-blocks-and-regions/)& [Content Types](modules/contenttype.md)  To understand Drupal you need to relate how its parts interact.  We understand that Drupal comes with Article and Basic Page Content Types.  We understand that each Content Type is set up to contain Fields and that we are in control of what Field we want include.  These fields might be simple text, titles, body, etc. but they might be images, maps, etc.  Since we may want to present different types of things on different pages of our website, we know we can create all sorts of Content Types, each with their own combinations of Fields.  If you are a database experienced person, you will be able to relate to the fact that these Fields populate rows of your database tables for the Content Types you are storing.

How do these Content Types relate to the action pages you present on your website?  If you think about it, the Menu bar you are providing is logically being shown consistently no matter which Content Type is presented.  So we know there is something bigger about a page than just the Content Type.  The overall page is made up of Regions.  The Regions are defined by the Theme you are using. You can see the Regions in your site by going to "Structure" in the Administrative interface of your site as a logged in site owner.  There you will see a list of Blocks and even a page mockup that shows were those Blocks are located on the overall page.  Typically, right in the middle you will see a Block called "Content" and that is where any Content Type is presented regardless of what type it is.  Around it you will see Navigation or Menu Blocks, Sidebars, Footers, and other stuff that makes up the overall Page.

## Block Control

Some of the prior statements about Blocks are more absolute than is the case.  [Drupal provides the ultimate in control.](https://www.webwash.net/courses/managing-blocks-in-drupal/)  You can [create a Block using Views](https://www.webwash.net/courses/managing-blocks-in-drupal/l/create-block-using-views-2/)  You can do things like include or [exclude, using the Block Exclude module,](https://www.webwash.net/courses/managing-blocks-in-drupal/l/using-block-exclude-pages/) for Blocks on different pages conditionally.  You can even [use the Views functionality to may grab headline or abstract information from a bunch of different pages and present them together](https://www.webwash.net/courses/managing-blocks-in-drupal/l/display-content-fields-in-block-using-views/) in the Content Region of a page.

## Block Visiblity Group module

The native Drupal application provides powerful conditional control over when a Block is or isn't presented.  However, the [Block Visiblity Group module](https://www.webwash.net/courses/managing-blocks-in-drupal/l/using-block-visibility-groups-module-2/  gives you a few more conditional combinations (think Boolean multiple) and perhaps more importantly, an ability to save conditional combinations to consistently apply in multiple areas without constant redundant effort.

## Blocks & Taxonomy

Besides differing Content Types or differing User Types or Publication Status, you can also take advantage of [Taxonomy](modules/taxonomy.md) to filter what is presented.    Here you will see how to set up a [filter using the most basic of taxomonmy call 'tags'](https://www.webwash.net/courses/managing-blocks-in-drupal/l/display-blocks-using-taxonomy-term-condition/) but you can do the same thing with your most complex hierarchical custom taxonomy as well.

## Token Filter module

You also probably already know that [Drupal has things called Tokens.](modules/development.md#token-module)  You might thing of these are the various fields available but it is really even larger than that because there are system generated type of fields for things like dates, times, status conditions, etc.  Now think about how powerful it is to further [control the display of your blocks by using tokens as filters;](https://www.youtube.com/watch?v=TKJyxTvH0Zw) for this you use the [Token Filter Module.](https://www.drupal.org/project/token_filter)



<br>
<br>
<br>

[Learn More - Drupal Modules List](../chapters.md#drupal-modules)
