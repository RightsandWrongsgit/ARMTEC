
# Misc Front-end Modules

Raw notes to clean up of possibly interesting front-end modules to check out, confirm value, categorize, and edit to a good entry:



May also consider adding this module for the capability that it enhances the normal link dialog in CKEditor to allow CSS classes, ID's, and Relation control (e.g. no follow, etc.).
composer require 'drupal/editor_advanced_link:^1.8'

The External Links module is a small module used to differentiate between internal and external links. Using jQuery, it will find all external links on a page and add an external icon  indicating it will take you offsite or a mail icon  for mailto: links.
composer require 'drupal/extlink:^1.6'

Flexslider module provides carousels and picture sliders; requires several configuration steps beyond the install and enable:
composer require 'drupal/flexslider:^2.0'
The flex slider Library is needed: http://flexslider.woothemes.com/
How TO: http://codekarate.com/daily-dose-of-drupal/drupal-8-flexslider-module
	https://www.youtube.com/watch?v=sKmmAL_dZtU&list=PLKdePeSydSBv9ro-	oJoxnhAFInyDdU4o9&index=1
COMPARE THIS TO SLICK CAROUSEL MODULE BEFORE COMMITTING:
composer require 'drupal/views_accordion:^2.0'
composer require 'drupal/views_slideshow:^4.8'

A pop up blocks. Use case might be cleaner log in, special offer with click through, ...
composer require 'drupal/simple_popup_blocks:^2.7'

This one needs serious testing and awaits Aimee's comments back on the sanity of even considering it.   But it offers Layout Builder on the fly block customization and export security potential risk reduction between environments.
composer require 'drupal/simple_block:^1.2'

Add classes to any block.  But make sure to test this with Layout Builder and the Bootstrap install because it requires modification of PHP level code at install.
composer require 'drupal/block_class:^1.3'


The Asset Injector Module is to inject both CSS and JS editor to tweak things without a full-fledged theme hack.  Consider it on a test site before jumping forward with it because it may be just as easy to do your own TWIG, HTML, CSS and JS editing without the overhead; so see how easy it is and if it carries negative overhead.
composer require 'drupal/asset_injector:^2.7'

composer require 'drupal/components:^3.0@beta'
Could be that the components module may offer some easy style editing via its GUI.  But you are probably better to stick with direct TWIG and CSS and JS editing.

[Looks cool but not Drupal 10 converted and maintainers seem to be missing in action](https://www.drupal.org/project/layoutcomponents)


<br>
<br>
<br>

[Learn More - CMS Front-end](../chapters.md#front-end)



