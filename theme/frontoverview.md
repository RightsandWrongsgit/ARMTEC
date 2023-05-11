
# Front-end Overview

Drupal [Content Management System (CMS)](chapters.md#chapter-content-management-system-cms) is an integrated website platform.  You select it because you have 'Content' that you wish to 'Display' in a user's 'Browser' in a 'Templated' manner which has some consistency.  A common example might be a newspaper which presents articles that have a title, subject, author, date, and story element consistently included in a template.  You might use the 'subject' to reference the sports, financial, lifestyle, business, and other sections in your newspaper.  In each of those sections you might 'present' the article in a slightly different style; font, color, size, etc.  Drupal has all the parts needed to control and manage the integrated workflow of all this stuff.

Think of the workflow like this:

Content→Database→PHP(core)→TWIG/HTML→CSS & JS→Display in Browser

The 'Content' is what you would write and it is stored in the 'Database' for each article in your newspaper.  The Drupal 'PHP' core has the code not only for a content type called 'Article' but you probably have other content types for, the newspaper's name, for advertisements, for your about the editor/publisher and contact each department type information, etc.  And all that defines your newspaper to the database so it knows where to store different parts.  And that also talks to the 'TWIG' layer which are templates for what goes in each region or section of your newspaper.  Now the look and feel of each section appear in their 'presention' is further managed by CCS or JavaScript(JS) that interact with the reader's browser. 

When we talk about the "Front-end" we are referencing the TWIG, HTML, CSS, and JS parts of your Drupal website that are key to managing how the content of your website is displayed.  Drupal core offers a 'theme' layer for this display called "Olivero".  You might also use themes offered by others and "Bootstrap" is a common powerhouse.  Underlying such themes is the "TWIG" templating engine and you can work with it directly.  At a more advanced level, there is "Decoupled" Drupal which might use Vue, React, or some other browser level framework that reaches back into Drupal to grab content but that does a lot more independently.

## Olivero

Drupal comes with a standard theme automatically.  The most current version of Drupal is using a presentation theme called [Olivero](../theme/olivero.md).  It is a relatively new addition that looks clean and modern.  For a fairly basic website you might give it a try.  It has a nice menu approach, is responsive for different devices, and it known for its accessiblity.  It is going through further updates and that might correct some potential limitations; because of some limits to your ability to customize certain parts of it you risk having your website sort of look generic. 

## Bootstrap

[Bootstrap](../theme/bootstrap.md) is one of the more common and powerful front-end frameworks.  It opens up a ton of flexiblity to go your own way with the look and feel of your website.  Flexibility is usually at the price of complexity and there is a little more to go this way.  However, because it is so commonly used, a version of [Bootstrap called Barrio](https://www.drupal.org/project/bootstrap_barrio) is set up specifically for use in Drupal.

## Alternatives

There are other alternatives that can be installed with Drupal. Right on the [Drupal website](http://Drupal.org) under the 'build' menu option you will find themes listed and a search function to look at some.  There are also commercially available themes but a watch out is that you need to be careful that the version of Drupal is supported before you buy one.  And, you might end up doing as much work with these commercial themes as just using the free ones as your starting point. 

## Install Themes

Installing a base theme is a straightforward process.  First, one theme came as default in what you installed Drupal.  [To install a Drupal theme](https://www.drupal.org/docs/user_guide/en/extend-theme-install.html) after you find it, you use [composer](../book/Novice.html#setting-up-your-basic-system) just like you do to install [Drupal modules](chapters.md#drupal-modules).  Keep in mind that you not only have to install it, but you need to set it as 'default' before it is the one that your website will be using.  To do that you go into ADMINISTRATION/APPEARANCE and install and make default.  The default theme files from Core are underneath the Core/themes subdirectory; <font color=red>YOU DO NOT EDIT ANYTHING IN CORE EVER!</font>  You can, however, copy stuff from core or from most 'contributed themes', into [your own custom theme's templates sub-directory (see last sub-directory listed in the red line section on this map)](../cicd/directorymap.html).  That is where any TWIG templates you will edit for your own unique proposes should be located. 

## TWIG

PHP itself renders a first level of HTML output but delivering it to TWIG templates. Those TWIG templates really goose things up a notch in terms of HTML display of your content.   Then, like in most website work, CSS and JS really leverage the power of display control.   

Drupal themes have TWIG templates.  Those templates are located in sub-directories under Drupal core are the base for any display that you haven't overridden.  You override them by installing 'contributed themes' in your themes sub-directory (see above note for location).  <font color=yellow>YOU DO NOT EDIT EITHER THE CORE OR CONTRIBUTED THEMES!</font>  This is because any updates to either as you refresh your site would then overwrite your edits and your work is screwed...  Rather, you make a custom theme in its own sub-directory.  Drupal, being as smart as it is, starts looking first in your custom theme sub-directory for a template, then falls back to the base contributed theme, and finally to the core base theme for any template backups it needs. What that customization for your own unique purpose is called is [creating a subtheme](../theme/twig.md#sub-theming).

It is very common that you might find a template under your base theme that you might want to tweak in some way; either across all places it is used on your site or on a specific page or node.  You are going to <font color=yellow>edit a copy of a twig template.</font>  TWIG templates are very similar to HTML with just three additional basic TWIG specific pieces of syntax; [how to proceed with your own TWIG edits is outlined here.](../theme/twig.md)

## Decoupled

Think of a de-coupled Drupal site as using something like a JavaScript(JS) framework like React or Vue and having it grab content from Drupal.  There are some performance benefits of a JS client inactive deployment.  There are also some breadth of device opportunities when we think of moving past computers, tables, and mobile to watches, smart TV's, vitual, other devices, and AI.  But all of these need the data or content and this brings in a real Drupal strength.  

You probably should think of decoupled as a continuum rather than a cleaver.  The front-end and back-end need to talk one way or another.  There have been some [bleeding edge attempts at decoupled Drupal and interesting bumps along the way](https://www.youtube.com/watch?v=RK4BG3hsN3I).  Excitement and reality have some tendency to diverge, so be careful on your approach.

Closer to home, there are a few current and emerging modules that might be considered.  For the options closer to home but that add capability, a review of a presentation from an Asheville Drupal Camp in the summer of 2020 is worth watching.  ['An Overview of Front End Component Integration Methods in Drupal'](https://www.youtube.com/watch?v=UQ-SRGVV9k8) is especially worth watching about 17 minutes into the video where two broad approaches to integration of components are compared.  One is 'Mapping Data In Code' and you can think of that as more at the TWIG or even PHP preprocessing level (which backend programmers probably gravitate toward).  The other is 'Mapping Data In Admin UI' and you can think of this as aiming toward integration with things like PatternLab and Storybook components.  This video is about understanding the options and their pros and cons; but it doesn't just boldly give an answer.

As discussed earlier, the variables from Drupal go through Twig Templates to provide a first level rendering of an entity like a page, block, etc.  You are going to want to work at the level of these templates at some point and we showed how different names, from generic to specific are shown with you have debug on.  To make that even easier, you might want to install and enable the Twig Debugger module that lets you click the little edit pencil from your GUI view of your page and then use your browser's 'source' view to see how that specific area of your page is controlled by a certain twig template (composer require drupal/twig_debugger and the drush en twig_debugger).

At the TWIG level two other helper modules are discussed in the video; 'Twig Field Value' and 'Twig Tweak'.  That later of these is broadly more capable so is worth considering.  The way to think about Twig Tweak as a module is that it aims to bring a richer toolset; but unlike a lot of modules don't necessarily think of it as a GUI keeping you away from code level efforts.  TWIG is a pretty rich framework in and of itself.  Drupal only brings a portion of it to bear.  What Twig Tweak will do is give you access to all the functions of the broader framework.  

At the practical level, take a look at 'How To Use Twig Tweak Module' here: https://www.youtube.com/watch?v=7UlGAeKYoa8



If you start getting into TWIG template editing, you may want to go to TwigFiddle.com where you can practice editing approaches. 


Components and how they fit with certain theme decisions:
The 'Map Data in Admin UI' direction is rapidly emerging.  As noted, not going to decoupled but that remains a possibility.  Instead, think about two 'Component' library or additions with Javascript that have developing or beta projects in Drupal aimed to facilitate their use integration; PatternLabs and Storybook.  Some of the PatternLabs modules are discussed in the back half of the 'An Overview of Front End Component Integration Methods in Drupal' video.  

Let's look at the Storybook emerging option.  First, Storybook itself can be found at https://storybook.js.org/  Note that it, like Drupal is also OpenSource.



When you look at Storybook, you will find it can be used with React, Angular, etc. and thus might be able to use the decoupled Drupal approach should you eventually go that way.  But for now, lets look at some Drupal modules that are specifically designed to integrate the two.  The Component Libraries Module works toward a regular Twig template combined with a metadata.json file describing the input data to connect the component JavaScript to the template.



Expect some pretty detailed set up steps but the documentation link to a GitLab repo read.me is pretty helpful in walking you through it. https://git.drupalcode.org/project/cl_server/-/blob/1.x/docs/storybook.md


To understand just how powerful and comprehensive Storybook is, you really need to go to the site and drive around.  You will see specific examples of components being deployed in many ways, even with links to access the underlying example code.  So if you are going to be doing a number of sites, it may be worth the trouble of the complex setup of the components so you have your own library.  And, of course, keep an eye out for others who publish their Drupal-Storybook Component to adopt. 

This module works with the Component Libraries: Theme Server.  You can go to the Theme Server module on Drupal.org and there is a link to a 'Step-by-Step' tutorial.


The newly release 'Component Libraries: Blocks' module it the third in this group that further expands the power of this approach.  It appears to integrate well with Views, Layout Builder, and other standard Drupal core common tools.



Bootstrap Barrio Theme:

How to set up your own subtheme using Bootstrap Barrio:
https://www.webwash.net/getting-started-with-bootstrap-4-using-barrio-in-drupal-8/


composer require 'drupal/bootstrap_sass:^5.0'

Confirm is the sass subtheme install automatically installs the barrio base theme; if not, here it is:
composer require 'drupal/bootstrap_barrio:^5.1'


If you want to load the bootstrap library locally you use this module; otherwise you set up the CDN approach in the first two.
composer require 'drupal/bootstrap_library:^1.14'

The Block Styles Module adds a styles selector at the end of the block configuration form.  Included styles support Bootstrap Styles on submodule for (modal, Dropdown, card, and collapse). The assumption is that a dependency on the Styles API will install it at the same time.
composer require 'drupal/block_styles:^2.0'

First try the above with Layout Builder native.  Then consider adding this views bootstrap module to get some potential additional functionality around accordion, carousel, etc. 
composer require 'drupal/views_bootstrap:^4.3'


May also consider adding this module for the capability that it enhances the normal link dialog in CKEditor to allow CSS classes, ID's, and Relation control (e.g. no follow, etc.).
composer require 'drupal/editor_advanced_link:^1.8'


External Link Pop up Modal warning of leaving site:
composer require 'drupal/bootstrap_external_link_popup:^2.0'


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


Potential libraries to see if they have anything worth adding and testing if they are even compatible with Bootstrap framework:
Animate.css
Hover.css


Potential free image sources -
	Pexels.com
unsplash.com/
upsplash.com


composer require 'drupal/components:^3.0@beta'
Could be that the components module may offer some easy style editing via its GUI.  But you are probably better to stick with direct TWIG and CSS and JS editing.


MODULES UNIQUE TO BOOTSTRAP THEME DECISION:
(Theme: Bootstrap Barrio)
N1ED Module:
Integrated them editor front-end for Bootstrap 4.  Think of this is the most integrated CKEditor Plugin available with a ton of widget features.  And because of the way it is built uniquely for CKEditor itself, it claims NOT to interfere with any of the other customization you might put in that editor (e.g. think about things like entity embedding).  

composer require drupal/n1ed
drush en n1ed


Views Bootstrap Module (NOTE: If you use the Bootstrap or Bootstrap Barrio theme):
This module has unique install instructions depending on the version of Bootstrap you are using in theming.  So go to the Drupa.org site for the latest install instructions. https://www.drupal.org/project/views_bootstrap



Bootstrap Layout Builder module:
If you want to use the GUI interface in modern Drupal to do much of your front-end work, consider using this module with your installed and default Bootstrap theme.  https://www.youtube.com/watch?v=sMbiqSMiZ6Y

composer require drupal/bootstrap_layout_builder
drush en bootstrap_layout_builder



Bootstrap Styles module:
This underlies the Bootstrap Layoutbuilder's styles plugins.

composer require drupal/bootstrap_styles
drush en bootstrap_styles



Bootstrap Layout Builder Section Library module:
This is key to saving reusable layout sections and whole templates within Bootstrap Layout builder's GUI interface so you can speed development by grabbing stuff from a library you build up specific to your site.  There is a library add on module that allows for sharing templates and discussion of establishing a repository of templates you might benefit from others work efforts. 

composer require drupal/section_library
drush en section_library

https://www.youtube.com/watch?v=-dhI5-Fs4qk OSTraining:: https://www.youtube.com/watch?v=E68DxSLcCd0
 


<br>
<br>
<br>

[Learn More - CMS Front-end](../chapters.md#front-end)
