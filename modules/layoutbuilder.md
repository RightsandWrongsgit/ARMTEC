
# Layouts

Building out how your site will look in Drupal is accomplished with a wide array of tools.  At a basic level you have a 'theme' and out of the box that theme is [Olivero.](https://armtec.services/theme/olivero.html)  You can see the [section on themes](theme/frontoverview.md) for a discussion of various options.  Within whatever theme you select as your foundation look and feel, you still can add and edit content, images, etc. to further refine how your site looks.  The Layout Builder discussed shortly provides a ton of goodies to achieve what you want.

## Drupal "Parts"

Typically a theme will provide some basic navigation, the general way Regions of a page are set up, a starting point of a color scheme; don't worry, you also have edit control of all that stuff as you gain experience and want to increasingly tune it to your own preferences.  Obviously more capable websites have not only many pages but often pages which support differing needs for various content chunks.  You might think of these in the Drupal world as Content Types or Content Entities.  Drupal adds that basic concept the ability to classify different content with tags or taxonomy; and it allows fine tuned control regarding who sees what with 'permissions by role'.  All of these [Drupal Basics](https://armtec.services/book/drupalbasics.html) also have a foundational impact on the design or layout of your website.<br>

## Same Page Preview
You can use Drupal without its simplified drag and drop Layout Builder interface and many people who are developers or site builders with some HTML and CSS experience prefer to do so.  Even in this more 'out of the box' situation, it is beneficial to see what your efforts look like in a real time preview. Thus you may just want to take a look a installing the [Same Page Preview module.](https://www.youtube.com/watch?v=Mh_plCpt1_A)  It can let you get a quick look at how simple it is to just try things with the core tools in the standard installation of Drupal and see how what you do plays out in an adjacent preview window.<br>

`composer require 'drupal/same_page_preview`<br>
`drush en same_page_preview`

<br>

# Using Layout Builder --

Layout Builder is a core module that comes automatically with your basic Drupal installation.  However, it is NOT turned on by default.  It offers more of a drag and drop interface for those who are at the Content Management:Site Builder level of experience.
Before you decide if it is for you take a look at [Getting started with Layout Builder.](https://www.webwash.net/getting-start-with-layout-builder-in-drupal/)  Then if you think it is for you you just need to go to the 'Administration/Extend' option on the menu bar and checkmark the Layout Builder module; remember to then "Save" and you should be ready to go.  If you are a command line person you can also enable it by simply typing ...<br>

`drush en layout_builder`

## Contributed Modules

### Layout Builder Plus

Layout Builder is extremely capable in and of itself.  If you balance toward the Content Manager more than the Site Builder you might want to start with an even more slimmed down initial interface called [Layout Builder +](https://www.youtube.com/watch?v=SYi3HmOcNyw) that has a starting "tab" for the most basic option and a secondary tab giving you access to the deeper options.  It will [pay dividends to have the Media Library](https://armtec.services/modules/media.md)set up with some of the image content you anticipate using on your site so you immediately get the feel for how all this works.




From Contributed modules -
composer require 'drupal/bootstrap_layout_builder:^2.0'
drush en bootstrap_layout_builder
composer require drupal/bootstrap_styles
drush en drupal/bootstrap_styles

[Layout Builder Components module](https://www.drupal.org/project/layoutcomponents)

[Introduction to Layout Paragraphs](https://www.youtube.com/watch?v=yl4JN-HLqbg)



In order to support background media on layout builder sections, this requires the following modules (if it doesn't install them automatically as dependencies, make sure you do it)
Media Library Form API Element
Media Library Theme Reset

"After enabling the module:
	•	Go to the settings tab at the modules configuration page, and complete the required mappings for both; image and local video entities & fields and configure the reset styles' plugins options"

composer require 'drupal/layout_builder_blocks:^1.0'
drush en layout_builder_blocks






The [Block Visibility Groups module](https://www.youtube.com/watch?v=ZKwkaMUbJIs) really allows powerful conditional control of what blocks show up for who and when.  You can have things show up differently depending on logged in status, different content type pages, potentially even Token filtered situations; the conditionals 'stack' to combine them for full control.<br>

`composer require 'drupal/block_visibility_groups`<br>
`drush en block_visibility_groups`



There are also "companion" modules for menu conditions, term conditions, token conditions, vocabulary conditions that you can add for easier control.





This module removes blocks completely from the system list and Layout Builder List. It could be used in combination with Layout Builder Restrictions. Use this module to remove blocks you won't use anywhere, then use Layout Builder Restrictions to fine-tune the listing per context. (replaces Block Blacklist).
composer require 'drupal/block_list_override:^1.0'
drush en block_list_override

composer require 'drupal/layout_builder_restrictions:^2.8'
drush en layout_builder_restrictions

composer require 'drupal/layout_builder_modal:^1.1'
drush en layout_builder_modal

composer require 'drupal/layout_builder_iframe_modal:^1.1'

composer require 'drupal/layout_builder_browser:^1.2'

composer require 'drupal/layout_builder_lock:^1.0@RC'


drush en media

drush en media_library
https://www.webwash.net/managing-media-assets-using-core-media-in-drupal/
SETUP REQUIRED: After installing these, go into your Text Editor and install the media library button into the toolbar. The above webwash link gives further instructions on what you need to do to allow the HTML tags.  There is also a list of supporting modules for different media types you might want to embed (e.g. instagram, Twitter, Flickr, Spotify, etc.)

Another SETUP article shows how you might also being the other entity types into the system:  https://texascreative.com/blog/drupal-8-basic-media-and-media-browser-setup-beginners

Entity Browser can add functionality beyond Media; which was basically put into Core with Drupal 8.8 or above.  If you want to embed entities beyond Media, consider installing this:
composer require 'drupal/entity_browser:^2.5'


Inline Entity Form – Create or Use custom block from within the content type that you have added the block field to and configured to use this module.
composer require 'drupal/inline_entity_form:^1.0@RC'
https://www.youtube.com/watch?v=PYTb-WwIt40
Companion to the inline entity form for maintaining revision history and rollback; especially with embedded entities.
composer require 'drupal/entity_reference_revisions:^1.9'


Off canvas layout builder block and media library integration tool:
composer require 'drupal/lb_claro:^1.0@beta'

See if it is still worthwhile to include Block Blacklist, Block Visibility Groups in plan.


[Bootstrap Layout Builder module](https://www.droptica.com/blog/streamlined-layout-builder-overview-bootstrap-layout-builder-module/)

Layout Builder Styles allows selection from a list of styles to apply to Blocks or Sections. The user has to define CSS based styles for element wrappers and then they can be selected for reuse. 
composer require 'drupal/layout_builder_styles:^1.0@beta'


Layout Builder Component Attributes allows for ID, Classes, Style, and Data attributes to be applied to blocks; leveraging CSS and JS.
composer require 'drupal/layout_builder_component_attributes:^1.2'

<br>
<br>
<br>

[Learn More - Drupal Modules List](../chapters.md#drupal-modules)

