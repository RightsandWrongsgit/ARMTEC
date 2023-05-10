
# Olivero Theme



https://evolvingweb.com/blog/hands-drupal-10-olivero-new-theme-meaningful-name




- Theming & Modules for some Good Specific Themes -
(You probably used a default theme as you laid out your fields, content types, blocks, etc.
Making your site look good leverages themes and you can do a lot to even customize the Core)

There is a lot of functionality right in Core.  You have a WYSIWYG editor, you have a media library for images, videos and more, you have the base theme, and you have the potential to leverage TWIG templates along with HTML, CSS, and JS in managing your presentation of you website.  The key thing to understand about Drupal is that it is a CMS or Content Management system and therefore, the first thing you are doing is setting up precise detail about what is in the content sections you will build.  So that is why thinking about fields, taxonomies, and the content types or nodes/blocks they will be presented in is the first order of business.  Making it look pretty with the theme you select, the images you apply, and the display of all the content happens after; the good news being that this separation of duties in Drupal allows you to later modify the look you present without having to redo all the content you have already dropped in.

Think of the work flow like this:

Content→Database→PHP(core)→TWIG/HTML→CSS & JS→View by user in Browser

PHP itself renders a first level of HTML output but delivering it to TWIG Templates really gooses things up a notch in terms of HTML display of your content and with HTML5 some might argue state management might be enough to be done at that level.  But most will want to further enhance with CSS and JS to really leverage the power of display control.   

Installing a base theme is a straightforward process.  First, one probably came by default in what you installed.  And if you want to change themes you go into ADMINISTRATION/APPEARANCE and install and make default a different one.  The default theme with Core are underneath the Core/themes subdirectory; YOU DO NOT EDIT ANYTHING IN CORE EVER!  You do, however, copy stuff from core, especially under your base theme's templates subdirectory which is where the TWIG templates live.


It is very common that you might find a template under your base theme that you might want to tweak in some way; either across all places it is used on your site or on a specific page or node.  You are only going to edit a copy of a twig template.  Note two things on the next image; a) there is a themes subdirectory at the same level as the core subdirectory and that is where you are going to put any customization to your base them (ie. where you are going to put the copy to edit) and b) there is a sites/default subdirectory also starting at that top level and in it is a services.yml file (which you can make by duplicating the default.services.yml file and renaming it).

The logic of messing with the services.yml file is that you are going to make one super simple edit within it.  Look down say 50-60 lines for the word 'debug:' and where it says false, change it to true and same the file.  Clear your cache and when you 'inspect source' on any page on your Drupal site you will find a list of the TWIG file that is active PLUS some suggested names of an 'override' file.  


Overriding is done all over Drupal as the way it is so flexible.  Drupal is a super CMS out of the box but the fact you can override all sorts of stuff makes it the best CMS out there to service a huge range of applications.  The TWIG template override is a first line of flexibility and the debug you just turned 'true' means the inspection of source will note a) where the template used in that area is located (helpful to find it to make a copy) at the bottom of the snippet below; b) the name of the currently used template (the one with 'x' in front of it below); and c) some alternative names you might consider for a copy you want to use as an override on the copy you are editing (from bottom upward, more general to more specific).  If you are overriding all uses of the current across your whole site you can keep the same name on the copy but if you are targeting the edit, think how focused you need it to be and move up the list accordingly. 


You aren't editing the original twig template in core, you are doing it to the copy under your custom theme.  In the example below, the subdirectory for that custom theme is named 'eg' and underneath it are subdirectories for 'templates' where the twig templates go and another subdirectory for 'css' styling.  It is standard practice in Drupal to separate your css into 'base', 'components', and 'layout'; so you see those as even deeper subdirectories in the image below.

In addition to having the twig and css assets in your custom theme subdirectories, you need to tell Drupal about where they are.  First you simply tell Drupal about what you are calling the custom theme and what base theme it is built upon in the file <yourcustomthemesname>.info.yml; in the example the custom them is simply called 'eg'.  See that file name in the same subdirectory at the css and templates subdirectories in the image above.

The content of that file are simple, as are most yml or yaml files.  The key thing when ever you do an of these file is the indents are TWO SPACES (so don't 'tab').  Here is what eg.info.yml looks like:


You also need to more specifically tell Drupal about the assets by showing where the css files you will use are located via <yourcustomthemesname>.libraries.yml; in the example at that same subdirectory level it is eg.libraries.yml and what is inside it is shown below:



The examples above are from some excellent training videos on YOUTUBE that Acquia has provided to the Drupal community.  Follow this link to the "Intro to twig templates" but make sure to watch those after it in the series to get a further understanding: https://www.youtube.com/watch?v=2cHe50tp_U4&list=PLpVC00PAQQxG0sW9YOueVgouRp4aj1bng&index=23


Beyond Core -

Drupal core is already very capable.  And there is even a tool called Layout Builder (in core, but must be enabled) and it really gives lots of ability to the newer users.   However, there are a ton of what are known as "front-end" options to use with Drupal; all the way to even doing a de-coupled site with a JS framework like React or Vue grabbing content from Drupal.  Closer to home, there are a few current and emerging modules that might be considered. 

For the options closer to home but that add capability, a review of a presentation from an Asheville Drupal Camp in the summer of 2020 is worth watching.  It is titled 'An Overview of Front End Component Integration Methods in Drupal' and can be found here:  https://www.youtube.com/watch?v=UQ-SRGVV9k8
About 17 minutes into the video two broad approached to integration of components is compared.  One is 'Mapping Data In Code'  and you can think of that as more at the TWIG or even PHP preprocessing level (which backend programmers probably gravitate toward).  The other is 'Mapping Data In Admin UI' and you can think of this as aiming toward integration with things like PatternLab and Storybook components.  This video is about understanding the options and their pros and cons; but it doesn't just boldly give an answer.

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

https://www.youtube.com/watch?v=-dhI5-Fs4qk OSTraining:: https://www.youtube.com/watch?v=E68DxSLcCd0
 


<br>
<br>
<br>

[Learn More - CMS Front-end](../chapters.md#front-end)
