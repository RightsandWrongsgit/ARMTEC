
# Using Layout Builder --

Set up Layout Builder with the modules to really make it work. [Getting started with Layout Builder.](https://www.webwash.net/getting-start-with-layout-builder-in-drupal/)

From Core -
drush en layout_builder




From Contributed modules -
composer require 'drupal/bootstrap_layout_builder:^2.0'
drush en bootstrap_layout_builder
composer require drupal/bootstrap_styles
drush en drupal/bootstrap_styles

[Introduction to Layout Paragraphs](https://www.youtube.com/watch?v=yl4JN-HLqbg)



In order to support background media on layout builder sections, this requires the following modules (if it doesn't install them automatically as dependencies, make sure you do it)
Media Library Form API Element
Media Library Theme Reset

"After enabling the module:
	•	Go to the settings tab at the modules configuration page, and complete the required mappings for both; image and local video entities & fields and configure the reset styles' plugins options"

composer require 'drupal/layout_builder_blocks:^1.0'
drush en layout_builder_blocks






The Block Visibility Groups module really allows powerful conditional control of what blocks show up for who and when.  You can have things show up differently depending on logged in status, different content type pages, potentially even Token filtered situations; the conditionals 'stack' to combine them for full control.
composer require 'drupal/block_visibility_groups:^1.4'
https://www.youtube.com/watch?v=ZKwkaMUbJIs
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

